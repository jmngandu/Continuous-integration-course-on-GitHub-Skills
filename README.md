
   _underscore_
   
 build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Run markdown lint
        run: |
          npm install remark-cli remark-preset-lint-consistent
          npx remark . --use remark-preset-lint-consistent --frail

      - uses: actions/upload-artifact@v3
        with:
          name: remark-lint-report
          path: public/

# FinancialFlowScripts - hledger-flow Custom Bank Scripts Template

This repository contains a template for using [hledger-flow](https://github.com/apauley/hledger-flow) with custom scripts tailored for various banks along with sample data. It demonstrates how to preprocess, import, and maintain financial data using automated workflows driven by hledger-flow and the hledger ledger tool.

## Features

- Custom scripts per bank for transaction extraction and data preprocessing
- Sample banking data demonstrating real-world transaction flow
- Automated import and ledger file generation via hledger-flow
- Generation of standard financial reports including Balance Sheet and Income Statement

## Prerequisites

- [hledger](https://hledger.org/) (latest version)
- [hledger-flow](https://github.com/apauley/hledger-flow) (latest version)
- [mise](https://mise.jdx.dev/getting-started.html) task runner to run tasks such as import and balance

## Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/bevsxyz/FinancialFlowScripts.git
   cd FinancialFlowScripts
   ```

2. Install required tools as per your platform's instructions:
   - mise (it will handle the rest)
   - hledger
   - hledger-flow

3. Review and adjust bank-specific script files in the `import/` directory if needed.

## Usage

### Clean

Remove generated intermediate files to start fresh:

```bash
mise run clean
```

### Import

Run the full import pipeline including all preprocessing and journal generation steps:
```bash
mise run import
```

### Balance Sheet

Generate the balance sheet report from all journal data:
```bash
mise run balance
```

Sample balance sheet output (as of 2024-04-06):
<link rel="stylesheet" href="hledger.css"><style>
table {border-collapse:collapse}
th, td {padding-left:1em}
th.account, td.account {padding-left:0;}
td:nth-child(1) {white-space:nowrap}
tr:nth-child(odd) td {background-color:#eee}
</style><table><tr><th colspan="2" style="text-align:left"><h2>Balance Sheet 2024-04-06</h2></th></tr><link rel="stylesheet" href="hledger.css"><style>
table {border-collapse:collapse}
th, td {padding-left:1em}
th.account, td.account {padding-left:0;}
</style><table><tr><th></th><th>2024-04-06</th></tr><tr><td colspan="2" class="account"><b>Assets</b></td></tr><tr><td class="account">Assets:Current:Bevan:HDFC:Cheque</td><td align="right" class="amount">₹2441.46</td></tr><tr><td style="border-top:double black" class="account"><b>Total:</b></td><td style="border-top:double black" align="right" class="amount coltotal"><b>₹2441.46</b></td></tr><tr><td colspan="2"> </td></tr><tr><td colspan="2" class="account"><b>Liabilities</b></td></tr><tr><td style="border-top:double black" class="account"><b>Total:</b></td><td style="border-top:double black" align="right" class="amount coltotal"><b>0</b></td></tr><tr><td colspan="2"> </td></tr><tr><td style="border-top:double black" class="account"><b>Net:</b></td><td style="border-top:double black" align="right" class="amount coltotal"><b>₹2441.46</b></td></tr></table></table>
## Project Structure

- `import/` — Contains raw bank data and preprocessing scripts
- `all-years.journal` — Generated ledger file with all imported data
- `mise.tool` — Defines `clean`, `import`, and `balance` tasks for convenience

## Contributing

Contributions to improve scripts for additional banks or sample data are welcome. Please submit pull requests or raise issues for suggestions and bugs.

## License

This project is licensed under the MIT License.


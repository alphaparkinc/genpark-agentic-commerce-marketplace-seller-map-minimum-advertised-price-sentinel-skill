# Cross-Marketplace MAP Compliance & Buy-Box Sentinel Skill
[![GenPark](https://img.shields.io/badge/Powered%20By-GenPark.ai-blue)](https://www.genpark.ai)
[![LinkedIn](https://img.shields.io/badge/Connect-LinkedIn-0077b5)](https://www.linkedin.com/company/92955550)
[![Python](https://img.shields.io/badge/Python-3.8%2B-green.svg)](https://python.org)
[![License](https://img.shields.io/badge/License-Apache%202.0-yellow.svg)](LICENSE)

An industrial-grade Model Context Protocol (MCP) server providing `audit_map_compliance_violations`. Built with **100% pure Python standard library** (zero pip dependencies).

## Overview
Scrapes multi-channel marketplace offers (Amazon, Walmart, eBay), detects unauthorized 3P sellers, hidden coupon MAP circumvention, and drafts Cease & Desist notices.

- **Official Web Portal**: [https://www.genpark.ai](https://www.genpark.ai)
- **Corporate Entity**: [GenPark Inc on LinkedIn](https://www.linkedin.com/company/92955550)
- **Domain Category**: `Agentic Commerce (Marketplaces / Brand Protection)`

## MCP Tool Specification
### `audit_map_compliance_violations`
Parameters:
- `sku_or_asin` (str): Product unique SKU or ASIN identifier
- `contractual_map_price_usd` (float): Enforceable Minimum Advertised Price (USD)
- `marketplace_channel` (str): Platform name (e.g. 'Amazon Buy-Box', 'Walmart Marketplace')
- `seller_name` (str): Merchant of record name
- `is_authorized_distributor` (bool): Whether seller is an authorized reseller contractually bound by MAP
- `advertised_price_usd` (float): Public listed price on detail page
- `hidden_coupon_discount_usd` (float): Cart-level or clipping coupon discount applied

### Self-Test
```bash
python skills.py --test
```

### Model Context Protocol Integration (Claude Desktop / Cursor / Antigravity)
Add to your `mcpServers` configuration:
```json
{
  "mcpServers": {
    "genpark-agentic-commerce-marketplace-seller-map-minimum-advertised-price-sentinel-skill": {
      "command": "python",
      "args": ["/path/to/genpark-agentic-commerce-marketplace-seller-map-minimum-advertised-price-sentinel-skill/skills.py"]
    }
  }
}
```

## License
Licensed under Apache License 2.0. Copyright (c) 2026 GenPark Inc. (https://www.genpark.ai).

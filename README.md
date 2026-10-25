# 이상 혼합물 기포점 압력 계산기

같은 온도의 성분별 포화증기압과 액상 조성으로 이상 용액에 첫 기포가 생기는 총압을 계산합니다.

- ID: E156
- App: https://nanalab.kr/eng-raoult-bubble-pressure/
- Repository: https://github.com/NaNaCompany/eng-raoult-bubble-pressure
- Formula: P = Σ(xᵢpᵢ*); Σxᵢ = 1

## Model and data

모든 증기압은 같은 온도에서의 값이어야 합니다. 이상 액상·이상 기상·증기와 액체의 평형을 가정하고 활동도계수·퓨가시티 보정·화학반응은 제외합니다. 비휘발성 성분은 증기압 0으로 입력할 수 있습니다. 액상 몰분율 합은 1이어야 하며 1e-10 이내 반올림 오차만 허용 후 정규화합니다. 증기상 조성이 아닌 액상 조성을 입력하세요.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.

# Changelog

All notable changes to this project will be documented in this file.

---

## [v0.2] - 2026-02-28

### ✨ New Features
- Added support for OpenAI-compatible image and video formats

### 🐛 Bug Fixes
- Fixed an issue where the project model required a second selection after setting a default model config
- Fixed an issue where `resolution` could not be read in certain cases
- Fixed model pipeline to use LangGraph
- Fixed missing default parameter selection
- Fixed billing being triggered even when billing was disabled
- Fixed openai-compatible provider being incorrectly identified as native OpenAI inference
- Fixed JSON parse failures

### ⚙️ Improvements
- Changed default billing mode to off
- Enhanced JSON format constraints for prompt output

---

## [v0.2.1] - 2026-02-28

### 🐛 Bug Fixes
- Fixed AI-generated content language not following the website language setting
- Fixed missing `Accept-Language` header in frontend API requests, causing locale to fall back to browser default

---

## [v0.1] - 2026-02-27

### 🎉 Initial Release
- First open-source release of the project

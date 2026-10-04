# YouTube Transcript Study Notes

![YouTube Transcript Study Notes promo](assets/promo.png)

Turn subtitles that are visibly present on a YouTube page into reviewable study notes: a summary, glossary, time anchors, and explicit gaps. It is useful for language learning, lesson review, and short-form video study without presenting guessed audio as a transcript.

Provide a video URL, target language, learning goal, and a user-selected `browserId`. The result is a Markdown draft grounded only in visible subtitles. If subtitles are absent, off, or in the wrong language, the Skill reports that limitation instead of inventing content.

## Install

```bash
npx skills add xxjrq/youtube-transcript-study-notes-free
```

## Requirement

This browser Skill requires [Easy WebBridge on GitHub](https://github.com/xxjrq/easy-webbridge); use [Gitee](https://gitee.com/xxjrq/easy-webbridge) as the fallback. The user selects one `browserId` for a run. The Skill keeps one task-owned session and tab group, never broadcasts to accounts, and closes only the session it created.

It is read-only by default. Login challenges, CAPTCHA, and security checks stop the run; they are never bypassed. Even when authorized to fill a draft, it never clicks a final publish or send button.

## Output

- Source URL, visible subtitle language, and covered range
- Summary supported by visible subtitle text
- Glossary entries with context and time anchors
- Explicit missing material and limitations

One run is limited to one chapter, scene, or short passage and at most 100 table rows. Larger material is split into batches rather than claimed as fully read.

## Self-test

```bash
node scripts/self-test.mjs
```

The self-test checks repository metadata, the 512px icon, and offline page-material simulation fixtures only. It does not contact YouTube or a browser.

## Sources and license

The business use was checked against [OpenCLI](https://github.com/jackwener/OpenCLI) and its [YouTube browser adapter documentation](https://github.com/jackwener/OpenCLI/blob/main/docs/adapters/browser/youtube.md). This repository contains original instructions and examples, and does not copy their implementation. Licensed under [MIT](LICENSE).

# draftcoach-data

Versioned public drafting data for the personal DraftCoach Android companion.

Feed: https://raw.githubusercontent.com/Wexp19/draftcoach-data/main/version.json

The Android app checks this manifest over HTTPS, validates the referenced snapshot's length, SHA-256, version, schema, hero references and engine compatibility, then retains it locally for offline use. Failed checks preserve the previous data. No login/token is required in the APK.

## Initial release

Release 1 contains 133 hero profiles. Ratings are coarse, provisional estimates, not measured win rates or professional tournament evidence. Patch 2.2.16a is a secondary-source report; see dataset provenance and confidence fields. Hero knowledge begins EXPERIMENTAL/LOW. Do not interpret this as saying established heroes were newly released.

The user prefers flexible, situational off-role drafting. Lane tags are evidence, not a hard hero whitelist; recommendations must still address the next team job and composition. Current Android scoring includes qualitative, user-selected seasonal map effects. Engine/map formulas are app code for now; a feed snapshot can tune supported hero data without an APK rebuild.

## Publishing

Keep release snapshots immutable under releases/<sequence>/dataset.json. Validate the complete candidate and run DraftCoach engine tests before publishing. Upload the new snapshot first, verify its public download/hash, then update version.json last with a greater sequence. Retain older releases for rollback. A failed gate must not change the manifest. No source credentials, screenshots, match history or personal player data belong here.

The companion project's scheduled patch checker runs daily at 17:00 Asia/Manila, subject to its automation runtime being available. It is not a guarantee of instant updates or verified meta quality. Changes require source evidence and confidence tracking; do not fabricate statistics.

## Sources checked for the seed

- https://mlbbhub.com/heroes
- https://mlbbhub.com/patch-notes
- https://mlbbguide.app/tr/content/3503357?channelId=2693844 (seasonal mechanics mirror)

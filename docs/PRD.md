# Sorted: Product Requirements Document (Public Edition)

**Publisher:** Product Zoned
**Platform:** Android
**Status:** In testing ahead of public release on Google Play
**Last updated:** September 2026

*This is a public edition of the product requirements. Commercial details and internal planning figures have been generalised or left out.*

---

## 1. Problem

When two people sit down to watch a film, the hardest part of the evening is often deciding what to watch. Streaming has made the choice almost limitless, and that abundance tends to produce paralysis rather than pleasure. Couples scroll through catalogues for long stretches, trade half-hearted suggestions, and frequently settle on something neither of them particularly wanted, or on something one of them has already seen. What was meant to be a relaxed evening becomes a small negotiation, and occasionally a small argument.

People watching alone face the same problem in a quieter form. With nobody to push back, a solitary viewer can drift through menus for just as long, simply because nothing compels a decision.

## 2. Objective

Sorted helps people settle on a film quickly, whether they are choosing alone or with a partner. It replaces open-ended browsing with a short, decisive swiping exercise that ends in a single agreed choice.

In the longer term, Sorted is intended to become a broader decision helper for leisure choices that suffer from the same problem of abundance, beginning with books, podcasts, and board games.

## 3. Product principles

1. **Decision over browsing.** Every screen should move the user closer to a choice. Filters are optional, and the fastest path from opening the app to swiping takes a single tap.
2. **Privacy as a feature rather than a disclaimer.** There are no accounts, no advertising, no analytics, and no tracking. Personal lists stay on the device, and any data that must leave it exists only for as long as a live session requires.
3. **Discovery rather than recital.** A matching app that surfaces only blockbusters adds little value, because users already know those titles. The deck should introduce films the user would not have thought of alone.
4. **Honest scope.** Features that are not ready appear as clearly disabled "coming soon" options, never as tappable dead ends.

## 4. Market context

The idea of swiping to agree on a film is a crowded category, with a number of apps built on near-identical mechanics, most of them framed around couples. Nearly every name assembled from words such as "movie," "match," "pick," and "swipe" has already been claimed. That saturation shaped the choice of "Sorted," a name that describes the outcome rather than the mechanic and leaves room for categories beyond film.

Sorted sets itself apart in four ways:

- **Privacy.** It needs no account and carries no advertising or analytics, whereas many alternatives require a sign-up or rely on advertising revenue.
- **Solo value.** Most alternatives assume two users. Sorted treats solo viewing as a primary use case, with character-led personas and a personal list mode.
- **Discovery.** The deck deliberately blends recognisable films with well-rated titles that are less widely known.
- **Platform ambition.** The underlying engine is category-agnostic, so it can later support books, podcasts, and board games.

## 5. Users

### 5.1 Segments considered

The analysis examined couples, groups of friends, and families across a range of living arrangements, group sizes, and viewing setups.

| Segment | Assessment |
|---|---|
| Couples | Watch together frequently, with a manageable set of constraints. **Prioritised.** |
| Solo viewers | Face the same paralysis without a partner to force a decision. **Added during the build as a primary segment.** |
| Groups of friends | Meet less regularly, often prefer conversation to a film, and are harder to satisfy collectively. **Deferred.** |
| Families | Require strict content sensitivity and have little tolerance for a poor suggestion. **Deferred.** |

### 5.2 Primary users for version 1

- A couple choosing a film together on two phones, whether they are in the same country or in different ones.
- A single viewer choosing a film alone, either guided by a persona or picking freely.

## 6. Scope for version 1

### 6.1 Flow

1. **Intro.** The headline reads "Stuck on what to do? Let's get you Sorted," followed by "Fewer arguments, less scrolling, more watching."
2. **Category.** The screen asks "What are you in the mood for?" Film is active, while books, podcasts, and board games appear as "coming soon."
3. **Mode.** The screen asks "Who's Sorting today?" and offers *Just me*, *Me and my person*, and *The whole crew* (coming soon).
4. **Solo style.** For *Just me*, the options are *Pick your movie buddy*, which uses a persona-curated deck; *Match with a stranger* (coming soon); and *I am my own best company*, a personal list mode.
5. **Filters.** This step is skipped in persona mode, because the persona defines the filters.
6. **Swiping.**
7. **Match or end of deck.**

### 6.2 Personas

Each persona applies its own filter to the deck, so that the four produce visibly different selections.

| Persona | Character | Taste |
|---|---|---|
| Noir | Older and refined, with a reverence for the classics | Highly rated dramas and classics from before 2000 |
| Dude | Young and easy-going, looking for something fun | Recent, shorter action, adventure, and comedy |
| Dame | Values substance over spectacle | Well-rated drama and mystery, with no action, war, or crime |
| Jaunty | Warm, whimsical, and drawn to feel-good stories | Family, romance, animation, and fantasy from the 1980s onward |

Early versions let Dude and Jaunty drift toward the same comedies, and Jaunty once returned almost nothing but animated films. Both problems were resolved by giving the two personas entirely separate genre sets. Each persona offers a short line in character whenever a match occurs.

### 6.3 Filters

Every filter is optional and defaults to "any," and a prominent "Start swiping" button lets the user bypass them altogether. Users can set their region, choose among the major subscription streaming services available where they live, and narrow the deck by genre, era, language, and minimum rating. An age-rating filter was considered and set aside, because the underlying certification data is incomplete for many titles and the persona genres already separate mature and family-friendly selections.

### 6.4 Discovery

When filters are broad, the deck blends recognisable titles with well-rated films of lower profile, rather than sorting purely by popularity. A rating floor ensures that a less popular film is still one worth watching. When the user narrows the filters deliberately, the deck respects those choices as given.

### 6.5 Swiping

- Swiping right accepts a film, and swiping left rejects it.
- Tapping **"Seen it"** marks a film as already watched, and it is kept out of future decks.
- Tapping **"More"** expands the card to show the full overview without triggering a swipe.

### 6.6 Matching

- In **couple mode**, a match occurs when both people swipe right on the same film.
- In **persona mode**, a match occurs when the user swipes right on a film within the persona's taste.
- In **I am my own best company**, the first right swipe produces the match and ends the round, so the mode yields a decision rather than an endless list.

### 6.7 End of deck

If the user reaches the end of the deck without a match, the app offers a way forward suited to the mode. Filter-based modes suggest casting a wider net, persona mode suggests trying a different buddy, and couple sessions end cleanly on both devices so that neither partner is left waiting.

### 6.8 Lists

A watchlist keeps matched films, and a watched list keeps films the user has already seen. Both live only on the device.

### 6.9 Navigation

Every screen after the intro offers a way home and a way to the watchlist. Leaving an active session asks for confirmation first, while leaving a finished session does not. All screens respect the phone's system insets, so content is never hidden behind gesture navigation or on-screen buttons.

## 7. Privacy

| Data | Where it lives | Retention |
|---|---|---|
| Watchlist and watched list | On the device only | Until the user removes items or uninstalls the app |
| Couple session data: a session code, identifiers that last only for that session, the host's country, the film deck, and each participant's swipes | A cloud database, used only to coordinate the two phones | Deleted when the session ends, or within about thirty minutes at the latest |
| Film information | Requested from The Movie Database (TMDB) | Governed by TMDB's own policy |

There are no accounts, no persistent device identifiers, no advertising, no analytics, and no crash-reporting tools. An earlier build kept a persistent random identifier on the device, and it was replaced with identifiers that exist only for the length of a session before release.

The full privacy policy is available at https://sorted-privacy-shield.lovable.app.

## 8. Business model

Version 1 is free, with no payments and no advertising. A modest subscription after a free trial, priced regionally, is under consideration for the future, and it will not come at the expense of the privacy principles above.

## 9. Measuring success

Early success will be judged by downloads, by how readily people swipe, and above all by how often a session ends in a match, since a match is the moment the product has done its job. Because Sorted collects no analytics by design, any engagement measurement will have to rely on privacy-preserving methods.

## 10. Known limitations

- In a couple session, the host's region determines the catalogue, so a matched film may be unavailable to a partner in another country.
- Watched lists are private to each device, so a film one partner has seen may still appear for the other.

## 11. Roadmap

**Next categories:** books, podcasts, and board games.

**Next modes:** *The whole crew* for groups, and *Match with a stranger*, which will require a user-chosen display name and a corresponding update to the privacy policy.

**Later:** availability checks across regions for couple sessions, a discovery setting that lets users choose between crowd-pleasers and films off the beaten path, and an iOS version.

---

*Film data and images are provided by The Movie Database (TMDB). This product uses the TMDB API but is not endorsed or certified by TMDB.*

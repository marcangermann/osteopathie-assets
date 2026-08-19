# Osteopathiezentrum Kamenz — Social Media Assets

Öffentliches Asset-Repo für Instagram-/Social-Media-Posts von **Osteopathiezentrum Kamenz**.

Dient ausschließlich als Bild-Hosting für die Meta Graph API (`image_url` muss öffentlich erreichbar sein). Enthält keine sensiblen Praxisdaten — nur fertige, veröffentlichungsreife Post-Grafiken.

## Struktur

```
instagram/
  YYYY-MM/
    YYYY-MM-DD_thema.png
```

Jede Datei entspricht genau einem veröffentlichten oder geplanten Instagram-Post. Dateiname = Post-Datum + Kurzthema.

## Verwendung (Raw-URL für die Graph API)

```
https://raw.githubusercontent.com/marcangermann/osteopathie-assets/main/instagram/YYYY-MM/YYYY-MM-DD_thema.png
```

Diese URL wird als `image_url` beim Erstellen des Media-Containers übergeben:

```
POST https://graph.facebook.com/v19.0/{ig_business_account_id}/media
  image_url=<raw_url>
  caption=<caption>
  access_token=<token>
```

Details zum vollständigen Publish-Workflow (Container erstellen → Status pollen → publishen) siehe Hermes-Skill `instagram-graph-api`.

## Posts (Log)

| Datum | Thema | Pfad | Post-ID |
|-------|-------|------|---------|
| 2026-08-19 | Casa Asado Weiterbildung (Zweibrücken) | `instagram/2026-08/2026-08-19_casa-asado.png` | pending |
| 2026-08-06 | Neuraltherapie (Maria Angermann) | `instagram/2026-08/2026-08-06_neuraltherapie.png` | `17959103156981360` |
| 2026-08-03 | Praxisurlaub (Rückkehr) | `instagram/2026-08/2026-08-03_praxisurlaub.png` | `18399857725092553` |

## Hinweise

- Nur fertige, freigegebene Grafiken committen — kein Zwischenstand.
- Bildformat: 1080×1080 px (quadratisch), PNG oder JPEG.
- Repo ist **öffentlich**, da die Graph API eine öffentlich erreichbare URL benötigt. Keine privaten/medizinischen Inhalte hier ablegen.

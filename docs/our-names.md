# Our names

Addresses the lf2 port names more than once, or names inside another symbol. The map holds the
guest-concept name; the port adopts it when it reads the generated constants.

| address | map name | lf2 port names |
|---|---|---|
| `0x0044D020` | `g_ScreenState` | `GX_SCREEN` (`cheats.c`), `SCREEN_WORD` (`world.h`) |
| `0x0044D064` | `g_MenuAction` | `GX_SCREEN` (`menu.c`): the same port name as `0x0044D020` for a different word |
| `0x0044FAF4` | `g_FontSheet0` | `FONT_SHEET_0` (`text.c`), `GLYPH_SHEET` (`objects.c`) |
| `0x00450B4C` | `g_PlayerDevice` (8 dwords) | `DEVSEL`, `PLAYER_DEVICE_1`, `NAME_MARK` (`objects.c`), `EBP` (`coop.c`); `PLAYER_DEVICE_2..4` are `+4`, `+8`, `+0xC`; `DEVSEL_END` is `+0x20` |
| `0x00451160` | `g_ModeMenuSelection` | `MENU_CURSOR`, `MODEMENU_SEL`, `MODEMENU_SEL_W` |
| `0x00455608` | `g_FrameSurface` | `FRAME_SURFACE`, `GLYPH_SURF` |
| `0x00457580` | `g_Click` | `GX_CLICK`, `CLICK_FLAG` |
| `0x00458B00` | `g_World` | `WORLD`, `ECX` (`world.h`), `BG_REGISTRY`, `GAME_TOP_MODE` |
| `0x004553BF` | `g_LocalPlayMarker` | `LOCAL_PLAY_MARKER`; it lies inside `g_KeyState` (`+0x47`) |
| `0x0043F010` | `Sprite_DrawClip` | `DRAW_CLIP`, override `fn_0043f010` |
| `0x0044D000` | (the `.data` section start) | `DATA_BASE` (`frame_capture.c`); not a symbol |

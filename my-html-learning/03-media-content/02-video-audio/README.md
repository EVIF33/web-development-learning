# Video and Audio in HTML

## Main rule

**Always provide multiple formats and captions.** No single format works everywhere. Video needs WebM/MP4, audio needs MP3/OGG, and both need fallback text.

## A bit of theory

### Video/audio element basics
- `<video>` embeds video files with controls.
- `<audio>` embeds audio files (no visual player by default).
- `src` attribute points to media file.
- `controls` adds play/pause/volume UI.
- **Formats:** MP4 (H.264), WebM, OGG - need multiple for compatibility.

### Key attributes
- `controls`: Shows player controls.
- `autoplay`: Starts playing automatically (avoid for UX).
- `loop`: Repeats when finished.
- `muted`: Starts with sound off (required for autoplay).
- `preload`: "auto"|"metadata"|"none" (loading strategy).
- `poster`: Preview image for video before play.

### Text tracks (subtitles/captions)
- `<track>` element inside `<video>`/`<audio>`.
- Formats: WebVTT (.vtt), SRT.
- Types: subtitles, captions, descriptions, chapters.
- `srclang` for language (en, ru, etc.).

## Rules for work

### Format compatibility

```html
<!-- Video with multiple sources -->
<video controls width="640" height="360" poster="preview.jpg">
  <source src="video.webm" type="video/webm">
  <source src="video.mp4" type="video/mp4">
  <p>Your browser doesn't support HTML5 video. 
     <a href="video.mp4">Download the video</a> instead.</p>
</video>
```

### Accessibility requirements
- Always include captions via `<track>` or YouTube/Vimeo.
- Provide transcript for audio-only content.
- Use aria-label for screen readers.
- Ensure keyboard controls work (space for play/pause).

### Performance optimization
- Compress videos: H.264 for MP4, VP9 for WebM.
- Use `preload="metadata"` for off-screen videos.
- Implement lazy loading with `loading="lazy"`.
- Consider CDN for large files.
- Provide lower quality alternatives for mobile.

### Mobile considerations
- iOS requires `playsinline` for inline playback.
- Autoplay only works with muted on mobile.
- Test on actual devices (emulators miss quirks).
- Consider data usage with `preload="none"`.

## What to remember

```html
<!-- Complete video example -->
<video controls 
       width="800" 
       height="450" 
       poster="thumbnail.jpg"
       preload="metadata"
       playsinline
       aria-label="Tutorial: How to optimize images for web">
  
  <!-- Multiple sources for compatibility -->
  <source src="tutorial.webm" type="video/webm">
  <source src="tutorial.mp4" type="video/mp4">
  
  <!-- Captions in multiple languages -->
  <track kind="subtitles" src="captions-en.vtt" srclang="en" label="English" default>
  <track kind="subtitles" src="captions-ru.vtt" srclang="ru" label="Russian">
  <track kind="captions" src="captions-en-cc.vtt" srclang="en" label="English (CC)">
  
  <!-- Fallback for old browsers -->
  <p>Download <a href="tutorial.mp4">MP4</a> or <a href="tutorial.webm">WebM</a> video.</p>
</video>

<!-- Complete audio example -->
<audio controls 
       preload="none"
       aria-label="Podcast episode about web development">
  <source src="podcast.mp3" type="audio/mpeg">
  <source src="podcast.ogg" type="audio/ogg; codecs=vorbis">
  <p>Listen to <a href="podcast.mp3">the podcast (MP3)</a>.</p>
</audio>
```
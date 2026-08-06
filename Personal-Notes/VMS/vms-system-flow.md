### VMS Working Flow

```text
Camera
   │
   │ Original RTSP
   ▼
VMS Staging
   │
   │ Restream RTSP
   ▼
Servers RTSP
   │
   │ Cloned RTSP streams
   ▼
VMS Server
   │
   │ Manage cameras, user, permissions
   ▼
VMS Client
   │
   ▼
Display monitors
```

- Camera create original RTSP stream -> VMS Staging collect it -> Send to RTSP Server -> Clone N stream flows -> VMS Server receives N flows -> VMS Client run to view

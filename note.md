# Notas: conexión de OpenClaw (VPS) con GitHub

**Problema:** `git push origin main` desde el VPS pedía usuario y contraseña, aunque la SSH key estaba bien (`ssh -T git@github.com` autentica como `pgsotos`).

**Causa probable (sin confirmar):** `origin` usaba HTTPS en ese momento; hoy ya es SSH (`git@github.com:pgsotos/openclaw-pgsotos.git`).

**Decisión:** creé un Personal Access Token e instalé GitHub CLI (`gh`) en el VPS para autenticar y desbloquear el push.

**Pendiente:** probar `git push origin main` solo con la SSH key. Si funciona, el PAT y `gh` ya no hacen falta para este repo.

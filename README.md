# Scoop Bucket for Beetroot

[Beetroot](https://github.com/mnardit/beetroot-releases) is a clipboard manager for Windows with AI-powered text transforms.

## Usage

```powershell
scoop bucket add beetroot https://github.com/mnardit/scoop-bucket
scoop install beetroot
```

## Update

Exit Beetroot from its tray menu before updating. For installations through 1.6.6, first repair the cached manifest's incorrect uninstaller filename:

```powershell
scoop update
$scoopRoot = if ($env:SCOOP) { $env:SCOOP } else { Join-Path $env:USERPROFILE 'scoop' }
& (Join-Path $scoopRoot 'buckets/beetroot/scripts/repair-beetroot.ps1') -AppDirectory (scoop prefix beetroot)
scoop update beetroot
```

The repair only changes the recognized old uninstaller field, retains an exact backup and does not delete application data. It is not needed for a fresh installation of 1.6.7 or later.

## Known Installation Issue

On September 9, 2026, Microsoft Defender intelligence 1.459.123.0 detected the official 1.6.7 installer as `Program:Win32/Wacapew.A!ml` in a Windows 11 test. The file has been submitted to Microsoft for analysis; an incorrect detection has not yet been confirmed. If Defender blocks installation, keep protection enabled and wait for the investigation or a subsequent release. Do not add exclusions to force installation. See the [distribution update](https://github.com/mnardit/beetroot-releases/pull/46).

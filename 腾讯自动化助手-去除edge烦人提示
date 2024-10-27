@echo off
:START
rem Start Microsoft Edge
echo [INFO] Starting Microsoft Edge...
start microsoft-edge:
rem Wait briefly to let the browser start properly
timeout /t 2 /nobreak >nul

echo [INFO] Microsoft Edge started at %date% %time%.

:CHECK
rem Check if Microsoft Edge process is running
echo [INFO] Checking if Microsoft Edge is still running...
tasklist /fi "imagename eq msedge.exe" 2>nul | findstr /r /c:"msedge.exe" >nul
if %errorlevel% neq 0 (
    rem If Microsoft Edge process not found, restart it
    echo [WARNING] Microsoft Edge has been closed. Restarting...
    goto START
) else (
    rem If the process is found, close Microsoft Edge and restart
    echo [INFO] Microsoft Edge is still running.
    echo [INFO] Closing Microsoft Edge for restart.
    taskkill /f /im msedge.exe >nul 2>&1
    rem Wait briefly to let the browser close properly
    timeout /t 2 /nobreak >nul
    echo [INFO] Microsoft Edge closed at %date% %time%.
    echo [INFO] Restarting Microsoft Edge...
    start microsoft-edge:
    rem Wait briefly to let the browser restart properly
    timeout /t 2 /nobreak >nul
    echo [INFO] Microsoft Edge restarted successfully at %date% %time%.
)

pause

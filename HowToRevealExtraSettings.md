### How To Reveal Extra Settings And Information In The UMC Control Panel

1. Go to the UMC Audio Driver Directory - if installed with default options it will be located at: C:\Program Files\BEHRINGER\UMC_Audio_Driver\x64

2. Use a code or text editor and open up the UMCAudioCplApp.xml file.

3. Change the sections that are marked Hidden to Visible. 
3a. You can also change some of the settings that are marked False to True (for example, the SerialNumber is set to False and thus not displayed. However you can change it to True and then you'll see it listed on the Info tab in the UMC Control Panel application once you save this file and restart. Please note that mine didn't have a serial number added, so that's probably why they marked the setting as false.

4. Save the file.
4a.Be sure to save the file with utf-8 encoding. If you open the file with a code editor like VSCode, this will save automatically with the encoding it had when you opened the file.

5. The code below is what my UMCAudioCPLApp.xml file looks like after I changed everything from Hidden to Visible, and from False to True.

6. Right-click on the UMC Control Panel in the system notifaction tray and exit the program.

7. Find the UMC Control Panel application and open it.

8. You should now see a lot of extra tabs in the control panel that show you a lot of extra information. Enjoy!

```
<?xml version="1.0" encoding="utf-8" ?>

<!-- Control Panel Configuration File
     For documentation see TUSBAudio_UserManual.pdf, section "Control Panel Customization".
-->

<ControlPanel FormatVersionMajor="3" FormatVersionMinor="0">
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <!-- GUID required to locate the driver DLL.
         IMORTANT: This GUID must be equal to the one specified in the
         InterfaceGUID= statement in custom.ini. -->
    <DriverInterfaceGUID>{215A80EF-69BD-4D85-AC71-0C6EA6E6BE17}</DriverInterfaceGUID>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <NotificationArea>
        <Enable>True</Enable>
    </NotificationArea>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageStatus>
        <!-- Supported values for this value: Hidden, Auto, Visible (default)  -->
        <SerialNumberVisibility>Visible</SerialNumberVisibility>
    </PageStatus>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageOptions>
        <!-- Supported values for this page: Hidden (default), Visible  -->
        <Visibility>Visible</Visibility>
    </PageOptions>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageStreamFormats>
        <!-- Supported values for this page: Hidden, Visible, Auto (default) -->
        <Visibility>Visible</Visibility>
    </PageStreamFormats>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageSampleRate>
        <!-- Supported values for this page: Hidden, Visible, Auto (default) -->
        <Visibility>Visible</Visibility>
    </PageSampleRate>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageClockSource>
        <!-- Supported values for this page: Hidden, Visible, Auto (default) -->
        <Visibility>Visible</Visibility>
    </PageClockSource>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageAsioDevice>
      <!-- Supported values for this page: Hidden, Visible, Auto (default) -->
      <Visibility>Visible</Visibility>
    </PageAsioDevice>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageBufferSettings>
        <!-- Supported values for this page: Hidden, Visible, Auto (default) -->
        <Visibility>Visible</Visibility>
        <!-- ................................................................ -->
        <BufferSettingsSection>
            <DisplaySafeMode>True</DisplaySafeMode>
        </BufferSettingsSection>
    </PageBufferSettings>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageVolumeControl>
        <!-- Supported values for this page: Hidden, Visible, Auto (default) -->
        <Visibility>Visible</Visibility>
    </PageVolumeControl>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageClientInfo>
        <!-- Supported values for this page: Hidden, Visible (default) -->
        <Visibility>Visible</Visibility>
    </PageClientInfo>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageInfo>
        <!-- Supported values for this page: Hidden, Visible (default) -->
        <Visibility>Visible</Visibility>
        <!-- ................................................................ -->
        <TableInfo>
            <DisplayManufacturer>True</DisplayManufacturer>
            <DisplayProduct>True</DisplayProduct>
            <DisplayVidPid>True</DisplayVidPid>
            <DisplayRevision>True</DisplayRevision>
            <DisplaySerialNumber>True</DisplaySerialNumber>
        </TableInfo>
    </PageInfo>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
    <PageAbout>
        <!-- Supported values for this page: Hidden, Visible (default) -->
        <Visibility>Visible</Visibility>
        <!-- ................................................................ -->
        <TableDriverInfo>
            <CustomVersion></CustomVersion>
            <DisplayVersion>True</DisplayVersion>
            <DisplayCopyright>True</DisplayCopyright>
        </TableDriverInfo>
    </PageAbout>
    <!-- ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++ -->
</ControlPanel>
```

# DefenderWatcher

## Introduction
WMI Watcher for Windows Defender Realtime Monitoring.
Remember to leave your Star to the Project! Thank you!

If you like my work and want to support it, then please consider to deposit a donation through Paypal by clicking on the next link: [www.paypal.me/SalvadorKrilewski](https://www.paypal.me/SalvadorKrilewski)

## How to use ?


1) Add the class "DefenderWatcher.vb" to your project.

2) Sample source using it . 

```vb
 ''' <summary>
 ''' The DefenderWatcher instance to monitor Windows Defender Realtime Status Changed.
 ''' </summary>
Friend WithEvents DefenderMon As New DefenderWatcher

 ''' ----------------------------------------------------------------------------------------------------
 ''' <summary>
 ''' Handles the <see cref="DefenderWatcher.DefenderStatusChanged"/> event of the <see cref="DefenderMon"/> instance.
 ''' </summary>
 ''' ----------------------------------------------------------------------------------------------------
 ''' <param name="sender">
 ''' The source of the event.
 ''' </param>
 ''' 
 ''' <param name="e">
 ''' The <see cref="DefenderWatcher.DefenderStatusChangedEventArgs"/> instance containing the event data.
 ''' </param>
 ''' ----------------------------------------------------------------------------------------------------
Private Sub DefenderMon_DefenderStatusChanged(ByVal sender As Object, ByVal e As DefenderWatcher.DefenderStatusChangedEventArgs) Handles DefenderMon.DefenderStatusChanged
    Dim sb As New System.Text.StringBuilder
    sb.AppendLine(" Defender Configuration change -  Windows Defender RealtimeMonitoring")
    sb.AppendLine(String.Format("DisableRealtimeMonitoring......: {0}", e.TargetInstance.ToString))
    sb.AppendLine(String.Format("Old Value......................: {0}", e.PreviousInstance.ToString))
    Me.BeginInvoke(Sub()
                       TextBox1.Text += (sb.ToString) & Environment.NewLine & Environment.NewLine
                   End Sub)
End Sub
```



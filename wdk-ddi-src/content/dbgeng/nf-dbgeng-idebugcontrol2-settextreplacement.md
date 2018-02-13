---
UID: NF:dbgeng.IDebugControl2.SetTextReplacement
title: IDebugControl2::SetTextReplacement method
author: windows-driver-content
description: The SetTextReplacement method sets the value of a user-named alias.
old-location: debugger\settextreplacement.htm
old-project: debugger
ms.assetid: 00c82e73-5649-403b-9f07-81bdd2f6c756
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetTextReplacement method [Windows Debugging], IDebugControl3 interface, debugger.settextreplacement, IDebugControl2, SetTextReplacement, dbgeng/IDebugControl2::SetTextReplacement, SetTextReplacement method [Windows Debugging], dbgeng/IDebugControl3::SetTextReplacement, IDebugControl2 interface [Windows Debugging], SetTextReplacement method, IDebugControl2::SetTextReplacement, SetTextReplacement method [Windows Debugging], IDebugControl2 interface, IDebugControl3::SetTextReplacement, IDebugControl_b53cd6ec-4cc4-45b2-96a0-b830bc7f8ca9.xml, IDebugControl3 interface [Windows Debugging], SetTextReplacement method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugControl2.SetTextReplacement
-	IDebugControl3.SetTextReplacement
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugControl2::SetTextReplacement method


## -description


The <b>SetTextReplacement</b>  method sets the value of a user-named alias.  


## -syntax


````
HRESULT SetTextReplacement(
  [in]           PCSTR SrcText,
  [in, optional] PCSTR DstText
);
````


## -parameters




### -param SrcText [in]

Specifies the name of the user-named alias.  The <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a> makes a copy of this string.  If <i>SrcText</i> is the same as the name of an automatic alias, the automatic alias is hidden by the new user-named alias.


### -param DstText [in, optional]

Specifies the value of the user-named alias.  The debugger engine makes a copy of this string.  If <i>DstText</i> is <b>NULL</b>, the user-named alias is removed.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 




## -remarks



Before executing commands or evaluating expressions, the debugger engine will replace the alias specified by <i>SrcText</i> with the value of the alias (specified by <i>DstText</i>).

If <i>SrcText</i> is an asterisk (<b>*</b>) and <i>DstText</i> is <b>NULL</b>, all user-named aliases are removed.  This is the same behavior as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a> method.

When an alias is changed by this method, the event callbacks are notified by passing the DEBUG_CES_TEXT_REPLACEMENTS flag to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550683">IDebugEventCallbacks::ChangeEngineState</a> callback method.

For an overview of aliases used by the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560047">Using Aliases</a>.  For more information about using aliases with the debugger engine API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551041">Interacting with the Engine</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556809">SetTextMacro</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553268">OutputTextReplacements</a>



<a href="https://msdn.microsoft.com/6e42122b-5a18-403b-a19a-1346bea8da12">as, aS (Set Alias)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554548">RemoveTextReplacements</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537997">ad (Delete Alias)</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol3.md">IDebugControl3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549280">GetTextReplacement</a>



<a href="..\dbgeng\nn-dbgeng-idebugcontrol2.md">IDebugControl2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl2::SetTextReplacement method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

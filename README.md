# AS3-ANE-COMs
This is COMs ANE for RS232, it's by Hanleon.
This ANE includ some functions, there are COM_Open(); COM_Close(); COM_Read() and COM_Write().
Also this ANE can connect more coms that using one ane.

-----------------------------------------------------------------------------
If connect single com, pleaase follow this code:

import com.hanleon.COMs
var ane: COMs = new COMs
ane.COM_Open(3,9600)
stage.addEventListener(Event.ENTER_FRAME, _onEF)
function _onEF(e: Event)
{
	trace(ane.COM_Read(3))
}
stage.addEventListener(MouseEvent.CLICK, _onCLICK)
function _onCLICK(e: MouseEvent)
{
	ane.COM_Write(3, "test123")
}

-----------------------------------------------------------------------------
If connect multi coms, pleaase follow this code:

import com.hanleon.COMs;
var ane: COMs = new COMs;
ane.COM_Open(3,9600);
ane.COM_Open(4,115200);
stage.addEventListener(Event.ENTER_FRAME, _onEF);
function _onEF(e: Event)
{
	trace(ane.COM_Read(3));
  trace(ane.COM_Read(4));
}
btn1.addEventListener(MouseEvent.CLICK, _onCLICK)
function _onCLICK(e: MouseEvent)
{
	ane.COM_Write(3, "test123")
}
btn2.addEventListener(MouseEvent.CLICK, _onCLICK)
function _onCLICK(e: MouseEvent)
{
	ane.COM_Write(4, "abc123")
}

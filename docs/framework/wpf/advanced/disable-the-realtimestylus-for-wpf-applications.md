---
title: WPF 응용 프로그램에 대해 RealTimeStylus를 사용하지 않도록 설정
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: e44b71ac5af64ab3a6cb008db71e5a8881592e91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962492"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>WPF 응용 프로그램에 대해 RealTimeStylus를 사용하지 않도록 설정
Windows Presentation Foundation (WPF)은 Windows 7 터치 입력을 처리 하는 것에 대 한 지원을 구축 했습니다. 지원으로 tablet 플랫폼의 실시간 스타일러스 입력을 통해 제공 됩니다 <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, 및 <xref:System.Windows.UIElement.OnStylusMove%2A> 이벤트입니다. 또한 Windows 7 WM_TOUCH Win32 창 메시지를 멀티 터치 입력을 제공합니다. 이러한 두 Api는 동일한 HWND에서 함께 사용할 수 없습니다. 사용 하지 않도록 설정 WM_TOUCH 메시지는 tablet 플랫폼 (WPF 응용 프로그램에 대 한 기본값)을 통해 터치 입력 합니다. 결과적으로, WM_TOUCH에 WPF 창에서 터치 메시지를 수신 하는 데 사용 하려면 WPF에서 기본 제공 스타일러스 지원을 해제 해야 합니다. WM_TOUCH를 사용 하는 구성 요소를 호스팅하는 WPF 창 등의 시나리오에 적용 됩니다.  
  
 스타일러스 입력에 수신 대기 하는 WPF를 사용 하지 않으려면 WPF 창에 추가 된 태블릿 지원을 제거 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플 코드는 리플렉션을 사용 하 여 기본 tablet 플랫폼 지원 기능을 제거 하는 방법을 보여 줍니다.  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>참고자료

- [스타일러스에서 입력 가로채기](intercepting-input-from-the-stylus.md)

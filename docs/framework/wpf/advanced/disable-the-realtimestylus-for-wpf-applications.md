---
title: 실시간스타일러스 비활성화
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: c2500b494f76c85e4b23823a44a180d85d5092ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186080"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>WPF 애플리케이션에 대해 RealTimeStylus를 사용하지 않도록 설정

윈도우 프리젠 테이션 재단 (WPF)는 윈도우 7 터치 입력을 처리하기위한 지원을 내장했다. 지원은 태블릿 플랫폼의 실시간 스타일러스 <xref:System.Windows.UIElement.OnStylusDown%2A>입력을 통해 <xref:System.Windows.UIElement.OnStylusUp%2A>제공됩니다. <xref:System.Windows.UIElement.OnStylusMove%2A> 윈도우 7 또한 Win32 WM_TOUCH 창 메시지와 같은 멀티 터치 입력을 제공 합니다. 이 두 API는 동일한 HWND에서 상호 배타적입니다. 태블릿 플랫폼(WPF 응용 프로그램의 기본값)을 통해 터치 입력을 사용하도록 설정하면 WM_TOUCH 메시지가 비활성화됩니다. 따라서 WM_TOUCH 사용하여 WPF 창에서 터치 메시지를 수신하려면 WPF에 기본 제공 스타일러스 지원을 사용하지 않도록 설정해야 합니다. 이는 WM_TOUCH 사용하는 구성 요소를 호스팅하는 WPF 창과 같은 시나리오에서 적용할 수 있습니다.  
  
 스타일러스 입력을 수신 대기하는 WPF를 사용하지 않으려면 WPF 창에 추가된 태블릿 지원을 제거합니다.  
  
## <a name="example"></a>예제  
 다음 샘플 코드에서는 리플렉션을 사용하여 기본 태블릿 플랫폼 지원을 제거하는 방법을 보여 주며 있습니다.  
  
```csharp  
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
  
## <a name="see-also"></a>참고 항목

- [스타일러스에서 입력 가로채기](intercepting-input-from-the-stylus.md)

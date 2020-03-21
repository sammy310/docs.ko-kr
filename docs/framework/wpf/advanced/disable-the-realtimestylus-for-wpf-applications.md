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
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="2bf21-102">WPF 애플리케이션에 대해 RealTimeStylus를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="2bf21-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="2bf21-103">윈도우 프리젠 테이션 재단 (WPF)는 윈도우 7 터치 입력을 처리하기위한 지원을 내장했다.</span><span class="sxs-lookup"><span data-stu-id="2bf21-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="2bf21-104">지원은 태블릿 플랫폼의 실시간 스타일러스 <xref:System.Windows.UIElement.OnStylusDown%2A>입력을 통해 <xref:System.Windows.UIElement.OnStylusUp%2A>제공됩니다. <xref:System.Windows.UIElement.OnStylusMove%2A></span><span class="sxs-lookup"><span data-stu-id="2bf21-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="2bf21-105">윈도우 7 또한 Win32 WM_TOUCH 창 메시지와 같은 멀티 터치 입력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf21-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="2bf21-106">이 두 API는 동일한 HWND에서 상호 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="2bf21-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="2bf21-107">태블릿 플랫폼(WPF 응용 프로그램의 기본값)을 통해 터치 입력을 사용하도록 설정하면 WM_TOUCH 메시지가 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bf21-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="2bf21-108">따라서 WM_TOUCH 사용하여 WPF 창에서 터치 메시지를 수신하려면 WPF에 기본 제공 스타일러스 지원을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf21-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="2bf21-109">이는 WM_TOUCH 사용하는 구성 요소를 호스팅하는 WPF 창과 같은 시나리오에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf21-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="2bf21-110">스타일러스 입력을 수신 대기하는 WPF를 사용하지 않으려면 WPF 창에 추가된 태블릿 지원을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf21-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bf21-111">예제</span><span class="sxs-lookup"><span data-stu-id="2bf21-111">Example</span></span>  
 <span data-ttu-id="2bf21-112">다음 샘플 코드에서는 리플렉션을 사용하여 기본 태블릿 플랫폼 지원을 제거하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf21-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2bf21-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bf21-113">See also</span></span>

- [<span data-ttu-id="2bf21-114">스타일러스에서 입력 가로채기</span><span class="sxs-lookup"><span data-stu-id="2bf21-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)

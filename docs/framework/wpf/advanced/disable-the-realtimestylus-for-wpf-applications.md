---
title: RealTimeStylus 사용 안 함
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: 74145c32af7e9ebbc774a0301e205aa1eb1539b3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737945"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="3e001-102">WPF 애플리케이션에 대해 RealTimeStylus를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="3e001-102">Disable the RealTimeStylus for WPF Applications</span></span>

<span data-ttu-id="3e001-103">WPF (Windows Presentation Foundation)는 Windows 7 touch 입력 처리를 기본적으로 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e001-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.</span></span> <span data-ttu-id="3e001-104">지원은 태블릿 플랫폼의 실시간 스타일러스 입력을 통해 <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>및 <xref:System.Windows.UIElement.OnStylusMove%2A> 이벤트로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e001-104">The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="3e001-105">또한 Windows 7은 Win32 WM_TOUCH 창 메시지로 다중 터치 입력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e001-105">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="3e001-106">이러한 두 Api는 동일한 HWND에서 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e001-106">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="3e001-107">태블릿 플랫폼 (WPF 응용 프로그램의 경우 기본값)을 통해 터치식 입력을 사용 하면 WM_TOUCH 메시지를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e001-107">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="3e001-108">따라서 WM_TOUCH를 사용 하 여 WPF 창에서 터치 메시지를 받으려면 WPF에서 기본 제공 스타일러스 지원을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e001-108">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="3e001-109">이는 WM_TOUCH를 사용 하는 구성 요소를 호스팅하는 WPF 창과 같은 시나리오에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e001-109">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="3e001-110">스타일러스 입력을 수신 하는 WPF를 사용 하지 않도록 설정 하려면 WPF 창에 의해 추가 된 태블릿 지원을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e001-110">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e001-111">예제</span><span class="sxs-lookup"><span data-stu-id="3e001-111">Example</span></span>  
 <span data-ttu-id="3e001-112">다음 샘플 코드에서는 리플렉션을 사용 하 여 기본 태블릿 플랫폼 지원을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e001-112">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3e001-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e001-113">See also</span></span>

- [<span data-ttu-id="3e001-114">스타일러스에서 입력 가로채기</span><span class="sxs-lookup"><span data-stu-id="3e001-114">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)

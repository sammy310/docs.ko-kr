---
title: WPF 및 Direct3D9 상호 운용성
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 1b14b823-69c4-4e8d-99e4-f6dade58f89a
ms.openlocfilehash: 38f5eb36e3e5c055c5a354a67e15cde8049a2967
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307732"
---
# <a name="wpf-and-direct3d9-interoperation"></a>WPF 및 Direct3D9 상호 운용성
Windows Presentation Foundation (WPF) 응용 프로그램에서 호스팅할 Direct3D9 콘텐츠를 포함할 수 있습니다. 이 항목에서는 WPF를 사용 하 여 효율적으로 상호 운용 되도록 Direct3D9 콘텐츠를 만드는 방법을 설명 합니다.  
  
> [!NOTE]
>  WPF에서 Direct3D9 콘텐츠를 사용할 때 성능에 대해 고려해 야 하는 합니다. 성능을 최적화 하는 방법에 대 한 자세한 내용은 참조 하세요. [Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항](performance-considerations-for-direct3d9-and-wpf-interoperability.md)합니다.  
  
## <a name="display-buffers"></a>버퍼를 표시 합니다.  
 <xref:System.Windows.Interop.D3DImage> 클래스 라고 하는 두 디스플레이 버퍼를 관리 합니다 *백 버퍼* 하며 *프런트 버퍼가*. 백 버퍼는 프로그램 Direct3D9 화면입니다. 백 버퍼에 대 한 변경 내용에 복사 됩니다 프런트 버퍼가 호출 하는 경우는 <xref:System.Windows.Interop.D3DImage.Unlock%2A> 메서드.  
  
 다음 그림에서는 백 버퍼 및 프런트 버퍼가 간의 관계를 보여 줍니다.  
  
 ![D3DImage 디스플레이 버퍼](./media/d3dimage-buffers.png "D3DImage_buffers")  
  
## <a name="direct3d9-device-creation"></a>Direct3D9 장치 만들기  
 Direct3D9 콘텐츠를 렌더링 하려면 Direct3D9 장치를 만들어야 합니다. 장치를 만드는 데 사용할 수 있는 Direct3D9 개체 두 개가 `IDirect3D9` 고 `IDirect3D9Ex`입니다. 이러한 개체를 만드는 데 `IDirect3DDevice9` 고 `IDirect3DDevice9Ex` 장치, 각각.  
  
 다음 방법 중 하나를 호출 하 여 장치를 만듭니다.  
  
-   `IDirect3D9 * Direct3DCreate9(UINT SDKVersion);`  
  
-   `HRESULT Direct3DCreate9Ex(UINT SDKVersion, IDirect3D9Ex **ppD3D);`  
  
 Windows Vista 또는 이후 운영 체제에서 사용 된 `Direct3DCreate9Ex` Windows 표시 드라이버 모델 (WDDM)를 사용 하도록 구성 된 표시를 사용 하 여 메서드. 사용 된 `Direct3DCreate9` 다른 플랫폼에서 메서드.  
  
### <a name="availability-of-the-direct3dcreate9ex-method"></a>가용성 Direct3DCreate9Ex 메서드  
 d3d9.dll에는 `Direct3DCreate9Ex` Windows Vista 또는 이후 운영 체제 에서만 메서드. 이 기능을 Windows XP에서 직접 연결 하면 응용 프로그램이 로드 되지 않습니다. 결정할 여부는 `Direct3DCreate9Ex` 메서드는 지원 DLL을 로드 하 고 프로시저 주소를 찾습니다. 다음 코드를 테스트 하는 방법을 보여 줍니다는 `Direct3DCreate9Ex` 메서드. 전체 코드 예제를 참조 하세요. [연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)합니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureD3DObjects](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensured3dobjects)]  
  
### <a name="hwnd-creation"></a>HWND 만들기  
 장치를 만드는 HWND 필요 합니다. 일반적으로 사용 하는 Direct3D9에 대 한 더미 HWND를 만듭니다. 다음 코드 예제에는 더미 HWND를 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_EnsureHWND](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_ensurehwnd)]  
  
### <a name="present-parameters"></a>현재 매개 변수  
 해야 장치를 만드는 `D3DPRESENT_PARAMETERS` 구조체 있지만 몇 가지 매개 변수만 중요 합니다. 이러한 매개 변수는 메모리 사용 공간을 최소화 하기 위해 선택 됩니다.  
  
 설정 된 `BackBufferHeight` 및 `BackBufferWidth` 1 필드입니다. 0으로 설정 하면 HWND의 크기를 설정할 수 있습니다.  
  
 항상 설정 합니다 `D3DCREATE_MULTITHREADED` 및 `D3DCREATE_FPU_PRESERVE` 방지 하기 위해 플래그 Direct3D9에서 호스팅할 Direct3D9 FPU 설정을 변경 하지 않도록 설정 하려면 사용 하는 메모리를 손상 시 키 지 합니다.  
  
 다음 코드를 초기화 하는 방법을 보여 줍니다는 `D3DPRESENT_PARAMETERS` 구조체입니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_Init](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_init)]  
  
## <a name="creating-the-back-buffer-render-target"></a>백 버퍼 렌더링 대상 만들기  
 호스팅할 Direct3D9 콘텐츠를 표시 하는 <xref:System.Windows.Interop.D3DImage>, Direct3D9 화면을 만들고 호출 하 여 할당을 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 메서드.  
  
### <a name="verifying-adapter-support"></a>어댑터 지원 확인  
 화면을 만들기 전에 모든 어댑터 화면 속성이 필요한 지를 확인 합니다. 어댑터를 하나만 렌더링 하는 경우에 시스템의 WPF 창의 모든 어댑터에서 표시 수 있습니다. 항상 다중 어댑터 구성을 처리 하는 Direct3D9 코드를 작성 해야 하 고 WPF 간에 사용 가능한 어댑터 화면을 이동할 수 있으므로 지원에 대 한 모든 어댑터를 확인 해야 합니다.  
  
 다음 코드 예제에서는 모든 어댑터가 Direct3D9 시스템에서 지 원하는 확인 하는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_TestSurfaceSettings](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_testsurfacesettings)]  
  
### <a name="creating-the-surface"></a>화면 만들기  
 화면을 만들기 전에 대상 운영 체제에서 장치 기능 좋은 성능을 지를 확인 합니다. 자세한 내용은 [Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항](performance-considerations-for-direct3d9-and-wpf-interoperability.md)합니다.  
  
 장치 기능을 확인 하는 경우에 화면을 만들 수 있습니다. 다음 코드 예제에는 렌더링 대상을 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#Renderer_CreateSurface](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderer_createsurface)]  
  
### <a name="wddm"></a>WDDM  
 Windows Vista 이상 운영 체제를 WDDM을 사용 하도록 구성 된 대상에 렌더링 대상 질감을 만들를 수준 0 화면을 전달 합니다 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 메서드. 잠글 수 있는 렌더링 대상 질감을 만들 수 없습니다. 성능은 저하 됩니다 때문에 Windows xp에서는이 방법은 권장 되지 않습니다.  
  
## <a name="handling-device-state"></a>장치 상태 처리  
 <xref:System.Windows.Interop.D3DImage> 클래스 라고 하는 두 디스플레이 버퍼를 관리 합니다 *백 버퍼* 하며 *프런트 버퍼가*. 백 버퍼는 프로그램 Direct3D 화면입니다.  백 버퍼에 대 한 변경 내용에 복사 됩니다 프런트 버퍼가 호출할 때를 <xref:System.Windows.Interop.D3DImage.Unlock%2A> 메서드를 하드웨어에 표시 됩니다. 경우에 따라 프런트 버퍼가 수 없게 됩니다. 화면 잠금, Direct3D 응용 프로그램을 제외 하는 전체 화면, 사용자 전환 또는 기타 시스템 활동과이 부족 한 가용성을 발생할 수 있습니다. WPF 응용 프로그램을 처리 하 여 알려집니다 이런 경우는 <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> 이벤트입니다.  응용 프로그램이 사용할 수 없게 되는 프런트 버퍼가에 반응 하는 방법을 소프트웨어 렌더링으로 대체 WPF 사용 여부에 따라 달라 집니다. <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 메서드 소프트웨어 렌더링으로 WPF 다시 속하는지 여부를 지정 하는 매개 변수를 받아들이는 오버 로드가 있습니다.  
  
 호출 하는 경우는 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%29> 오버 로드 하거나 호출 합니다 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> 오버 로드는 `enableSoftwareFallback` 매개 변수 설정 `false`, 프런트 버퍼를 사용할 수 없게 하 고 아무 것도 렌더링 시스템 백 버퍼에 대 한 참조를 해제 표시 됩니다. 프런트 버퍼가 다시 제공 되 면 렌더링 발생을 <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> WPF 응용 프로그램에 알리는 이벤트입니다.  에 대 한 이벤트 처리기를 만들 수는 <xref:System.Windows.Interop.D3DImage.IsFrontBufferAvailableChanged> 유효한 Direct3D 화면을 사용 하 여 다시 렌더링을 다시 시작 하는 이벤트입니다. 렌더링을 다시 시작 하려면 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A>합니다.  
  
 호출 하는 경우는 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%28System.Windows.Interop.D3DResourceType%2CSystem.IntPtr%2CSystem.Boolean%29> 오버 로드는 `enableSoftwareFallback` 매개 변수 설정 `true`를 호출 하지 않아도 되므로 프런트 버퍼를 사용할 수 없을 때 렌더링 시스템은 백 버퍼에 대 한 참조를 유지 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 때 앞 버퍼를 다시 사용할 수 있습니다.  
  
 소프트웨어 렌더링을 사용 하는 경우 여기서 사용자의 장치를 사용할 수 없지만 렌더링 시스템은 Direct3D 화면에 대 한 참조를 유지 하는 경우 있을 수 있습니다. Direct3D9 장치를 사용할 수 있는지를 확인 하려면 호출을 `TestCooperativeLevel` 메서드. Direct3D9Ex 장치 호출을 확인 하는 `CheckDeviceState` 메서드를 때문에 `TestCooperativeLevel` 메서드는 사용 되지 않으며 항상 성공 반환 합니다. 사용자 장치를 사용할 경우 호출 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 백 버퍼에 대 한 WPF의 참조를 해제 합니다.  장치를 재설정 해야 할 경우 호출 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 사용 하 여는 `backBuffer` 매개 변수 설정 `null`, 다음 호출 <xref:System.Windows.Interop.D3DImage.SetBackBuffer%2A> 사용 하 여 다시 `backBuffer` 유효한 Direct3D 화면을로 설정 합니다.  
  
 호출 된 `Reset` 다중 어댑터 지원을 구현 하는 경우에 잘못 된 장치에서 복구 하는 방법입니다. 아니면 모든 Direct3D9 인터페이스를 해제 하 고 전체적으로 다시 만듭니다. 어댑터 레이아웃 변경 된 경우에 변경 전에 만들어진 Direct3D9 개체 업데이트 되지 않습니다.  
  
## <a name="handling-resizing"></a>크기 조정을 처리합니다.  
 경우는 <xref:System.Windows.Interop.D3DImage> 표시 됩니다 현재에 따라 확장은 기본 크기로 이외의 해상도 <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A>점을 제외 하 고 <xref:System.Windows.Media.Effects.SamplingMode.Bilinear> 대체 <xref:System.Windows.Media.BitmapScalingMode.Fant>합니다.  
  
 충실도 높아집니다, 필요한 경우 새로 만들어야 합니다 노출 하는 경우의 컨테이너는 <xref:System.Windows.Interop.D3DImage> 크기를 변경 합니다.  
  
 세 가지 방법으로 크기 조정 처리할 수 있습니다.  
  
-   레이아웃 시스템에 참여 하 고 크기를 변경할 경우 새 화면을 만듭니다. 가 소진 되어 수도 비디오 메모리 조각화 때문에 화면을 너무 많이 만들지 마십시오.  
  
-   새 화면을 만들려면 고정된 기간 크기 조정 이벤트를 발생 하지 않은 때까지 기다립니다.  
  
-   만들기는 <xref:System.Windows.Threading.DispatcherTimer> 컨테이너 크기를 초당 여러 번 확인 하는 합니다.  
  
## <a name="multi-monitor-optimization"></a>다중 모니터 최적화  
 렌더링 시스템으로 이동 하는 경우 성능이 크게 저하 될 수 있습니다는 <xref:System.Windows.Interop.D3DImage> 다른 모니터로 합니다.  
  
 그러나 WDDM에 동일한 비디오 모니터 되는 카드를 사용 하 여 `Direct3DCreate9Ex`, 성능이 저하 되지 않습니다. 모니터는 별도 비디오 카드에 있는 경우 성능이 저하 됩니다. Windows xp에서는 성능이 항상 저하 됩니다.  
  
 경우는 <xref:System.Windows.Interop.D3DImage> 좋은 성능을 복원 하려면 해당 어댑터에 새 화면을 만들 수 있습니다 다른 모니터로 이동 합니다.  
  
 성능 저하를 방지 하려면 다중 모니터에 맞게 코드를 작성 합니다. 다음은 다중 모니터 코드를 작성 하는 한 가지 방법은 보여 줍니다.  
  
1. 지점을 찾는 합니다 <xref:System.Windows.Interop.D3DImage> 화면 공간에는 `Visual.ProjectToScreen` 메서드.  
  
2. 사용 된 `MonitorFromPoint` GDI 메서드 시점을 표시 하는 모니터를 찾습니다.  
  
3. 사용 된 `IDirect3D9::GetAdapterMonitor` 모니터 Direct3D9 어댑터를 찾으려면 메서드는 합니다.  
  
4. 어댑터 백 버퍼를 사용 하 여 어댑터와 동일 하 게 없는 경우 새 백 버퍼에 새 모니터 만들고 할당 하 여 <xref:System.Windows.Interop.D3DImage> 백 버퍼입니다.  
  
> [!NOTE]
>  경우는 <xref:System.Windows.Interop.D3DImage> 여러 모니터 성능 WDDM의 경우 제외 하 고 느려질 수 및 `IDirect3D9Ex` 동일한 어댑터에 있습니다. 이 상황에서 성능을 향상 시키는 방법이 없습니다.  
  
 다음 코드 예제에는 현재 모니터를 찾는 방법을 보여 줍니다.  
  
 [!code-cpp[System.Windows.Interop.D3DImage#RendererManager_SetAdapter](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanager_setadapter)]  
  
 모니터를 업데이트 때 합니다 <xref:System.Windows.Interop.D3DImage> 컨테이너의 크기 또는 위치 변경 또는 업데이트를 사용 하 여 모니터를 `DispatcherTimer` 초당 여러 번 업데이트 하는 합니다.  
  
## <a name="wpf-software-rendering"></a>WPF 소프트웨어 렌더링  
 WPF는 다음과 같은 경우에는 소프트웨어에서 UI 스레드에서 동기적으로 렌더링합니다.  
  
-   인쇄  
  
-   <xref:System.Windows.Media.Effects.BitmapEffect>  
  
-   <xref:System.Windows.Media.Imaging.RenderTargetBitmap>  
  
 이러한 상황 중 하나가 발생 하면 렌더링 시스템 호출을 <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> 소프트웨어 하드웨어 버퍼를 복사 하는 방법입니다. 기본 구현 호출을 `GetRenderTargetData` 에 화면을 사용 하 여 메서드. 이 호출은 잠금/잠금 해제 패턴 외부에서 발생 하기 때문에 실패할 수 있습니다. 이 경우에 `CopyBackBuffer` 메서드가 반환 되는 `null` 및 이미지가 표시 되지 않습니다.  
  
 재정의할 수 있습니다 합니다 <xref:System.Windows.Interop.D3DImage.CopyBackBuffer%2A> 메서드를 기본 구현을 반환 하는 경우 및 `null`, 자리 표시자를 반환할 수 있습니다 <xref:System.Windows.Media.Imaging.BitmapSource>합니다.  
  
 또한 기본 구현을 호출 하는 대신 고유한 소프트웨어 렌더링을 구현할 수 있습니다.  
  
> [!NOTE]
>  WPF가 완전히 소프트웨어에서 렌더링 하는 경우 <xref:System.Windows.Interop.D3DImage> WPF 프런트 버퍼가 없기 때문에 표시 되지 않습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Interop.D3DImage>
- [Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [연습: WPF에서 Direct3D9 콘텐츠 호스팅](walkthrough-hosting-direct3d9-content-in-wpf.md)

---
title: Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], Direct3D9 interop performance
- Direct3D9 [WPF interoperability], performance
ms.assetid: ea8baf91-12fe-4b44-ac4d-477110ab14dd
ms.openlocfilehash: fd3c99f22a1d097c82494ba6eff344820162ed87
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356730"
---
# <a name="performance-considerations-for-direct3d9-and-wpf-interoperability"></a>Direct3D9 및 WPF 상호 운용성을 위한 성능 고려 사항
사용 하 여 호스팅할 Direct3D9 콘텐츠를 호스트할 수 있습니다는 <xref:System.Windows.Interop.D3DImage> 클래스입니다. Direct3D9 콘텐츠 호스팅 응용 프로그램의 성능 영향을 줄 수 있습니다. 이 항목에서는 Windows Presentation Foundation (WPF) 응용 프로그램에서 호스팅할 Direct3D9 콘텐츠 호스팅 때 성능을 최적화 하기 위한 모범 사례를 설명 합니다. 이러한 모범 사례를 사용 하는 방법을 포함 <xref:System.Windows.Interop.D3DImage> 및 Windows Vista, Windows XP를 사용 하 고 다중 모니터를 표시 하는 경우 모범 사례입니다.  
  
> [!NOTE]
>  이러한 모범 사례를 보여 주는 코드 예제를 보려면 [WPF 및 Direct3D9 상호 운용성](wpf-and-direct3d9-interoperation.md)합니다.  
  
## <a name="use-d3dimage-sparingly"></a>D3DImage를 제한적으로 사용  
 호스팅할 Direct3D9 콘텐츠 호스트는 <xref:System.Windows.Interop.D3DImage> 순수 Direct3D 응용 프로그램을 빠르지으로 인스턴스를 렌더링 하지 않습니다. 화면 복사 및 명령 버퍼를 플러시하는 비용이 많이 드는 작업을 수 있습니다. 수가 <xref:System.Windows.Interop.D3DImage> 인스턴스 증가 하는 경우 자세한 플러시 발생 하 고 성능이 저하 됩니다. 사용 해야 하므로 <xref:System.Windows.Interop.D3DImage> 제한적입니다.  
  
## <a name="best-practices-on-windows-vista"></a>Windows Vista에 대 한 모범 사례  
 Windows 표시 드라이버 모델 (WDDM)를 사용 하도록 구성 된 표시를 사용 하 여 Windows Vista에서 최상의 성능을 위해에서 호스팅할 Direct3D9 화면에 만들기는 `IDirect3DDevice9Ex` 장치입니다. 이렇게 하면 화면을 공유할 수 있습니다. 비디오 카드를 지원 해야 합니다 `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` 및 `D3DCAPS2_CANSHARERESOURCE` Windows Vista의 드라이버 기능입니다. 다른 모든 설정을 인해 성능이 크게 저하는 소프트웨어를 통해 복사할 화면.  
  
> [!NOTE]
>  Windows Vista 표시와 관련 된 Windows XP 표시 드라이버 모델 (XDDM)를 사용 하도록 구성 되어 있으면 설정에 관계 없이 소프트웨어를 통해 화면에 항상 복사 됩니다. 적절 한 설정 및 비디오 카드를 사용 하 여 노출 복사본은 하드웨어에서 수행 되기 때문에 WDDM을 사용 하는 경우 Windows Vista 더 나은 성능을 표시 됩니다.  
  
## <a name="best-practices-on-windows-xp"></a>Windows XP에 대 한 모범 사례  
 Windows xp에서는 Windows XP 디스플레이 드라이버 모델 (XDDM)를 사용 하는 최상의 성능을 위해 잘못 동작 하는 잠금 화면을 만들 때의 `IDirect3DSurface9::GetDC` 메서드가 호출 됩니다. 내부적으로 `BitBlt` 메서드 하드웨어에서 장치의 화면을 전송 합니다. `GetDC` 메서드 xrgb 항상 작동 합니다. 그러나 클라이언트 컴퓨터는 SP3 또는 SP2, Windows XP를 실행 하는 경우와 클라이언트에 계층화 된 창 기능에 대 한 핫픽스 있으면이 방법을 ARGB 화면 합니다. 비디오 카드를 지원 해야 합니다는 `D3DDEVCAPS2_CAN_STRETCHRECT_FROM_TEXTURES` 드라이버 기능입니다.  
  
 16 비트 데스크톱 디스플레이 깊이 성능을 크게 줄일 수 있습니다. 32 비트 데스크톱을 사용 하는 것이 좋습니다.  
  
 Windows Vista 및 Windows XP를 개발 하는 경우에 Windows XP의 성능을 테스트 합니다. Windows xp 비디오 메모리 부족 문제가 중요 합니다. 또한 <xref:System.Windows.Interop.D3DImage> Windows XP에서 Windows Vista WDDM 필요한 추가 비디오 메모리 복사본으로 인해 보다 자세한 대역폭과 비디오 메모리를 사용 합니다. 따라서 동일한 비디오 하드웨어에 대 한 보다 Windows Vista에서 Windows XP에서 뒤 처 집니다 성능을 예상할 수 있습니다.  
  
> [!NOTE]
>  XDDM은 Windows XP와 Windows Vista;에서 제공 됩니다. 그러나 WDDM은 Windows Vista 에서만 사용할 수 있습니다.  
  
## <a name="general-best-practices"></a>일반 모범 사례  
 장치를 만들 때 사용 된 `D3DCREATE_MULTITHREADED` 생성 플래그입니다. 성능 줄어들지만 WPF 렌더링 시스템 다른 스레드에서이 장치에서 메서드를 호출 합니다. 사용할 두 스레드가 동시에 장치에 액세스할 수 있도록 잠금 프로토콜을 올바르게 수행 해야 합니다.  
  
 렌더링을 관리 하는 WPF 스레드에서 수행 것이 좋습니다 사용 하 여 장치를 만들어야 합니다 `D3DCREATE_FPU_PRESERVE` 생성 플래그입니다. 이 설정이 없으면 D3D 렌더링 WPF 배정밀도 연산의 정확도 줄일 하 고 렌더링 문제가 발생할 수 있습니다.  
  
 바둑판식를 <xref:System.Windows.Interop.D3DImage> 하드웨어 지원 없이 비 pow2 화면을 타일 되거나 바둑판식으로 배열 하는 경우에 빠르지만 <xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush> 를 포함 하는 <xref:System.Windows.Interop.D3DImage>.  
  
## <a name="best-practices-for-multi-monitor-displays"></a>다중 모니터 디스플레이 대 한 모범 사례  
 여러 모니터에 있는 컴퓨터를 사용 하는 경우에 앞에서 설명한 모범 사례를 따라야 합니다. 다중 모니터 구성에 대 한 몇 가지 추가 성능 고려 사항이 있습니다.  
  
 백 버퍼를 만들 때 특정 장치에 어댑터를 만든 있지만 WPF 모든 어댑터에 프런트 버퍼를 표시할 수 있습니다. 프런트 버퍼가 업데이트 하기 위해 어댑터를 통해 복사 하는 것은 비용이 매우 많이 들 수 있습니다. 여러 비디오 카드와 WDDM을 사용 하도록 구성 된 Windows vista는 `IDirect3DDevice9Ex` 장치 성능 저하가 발생 하지 방법이 다른 어댑터 있지만 동일한 비디오 카드에 프런트 버퍼가 있으면 합니다. 그러나 Windows XP에 여러 개의 비디오 카드를 사용 하 여 XDDM 경우 성능이 크게 저하 프런트 버퍼가 백 버퍼 다른 어댑터에 표시 되 면 자세한 내용은 [WPF 및 Direct3D9 상호 운용성](wpf-and-direct3d9-interoperation.md)합니다.  
  
## <a name="performance-summary"></a>성능 요약  
 다음 표에서 운영 체제, 픽셀 형식 및 화면 잠금 가능성의 함수로 프런트 버퍼가 업데이트의 성능을 보여 줍니다. 프런트 버퍼가 및 백 버퍼 동일한 어댑터에 있는 것으로 간주 됩니다. 어댑터 구성에 따라 하드웨어 업데이트는 일반적으로 소프트웨어 업데이트 보다 훨씬 빠릅니다.  
  
|화면 픽셀 형식|Windows Vista, WDDM 및 9Ex|다른 Windows Vista 구성|Windows XP SP3 또는 SP2 핫픽스 (포함)|Windows XP SP2|  
|--------------------------|---------------------------------|----------------------------------------|--------------------------------------|--------------------|  
|D3DFMT_X8R8G8B8 (잠글 수 없습니다)|**하드웨어 업데이트**|소프트웨어 업데이트|소프트웨어 업데이트|소프트웨어 업데이트|  
|D3DFMT_X8R8G8B8 (잠금)|**하드웨어 업데이트**|소프트웨어 업데이트|**하드웨어 업데이트**|**하드웨어 업데이트**|  
|D3DFMT_A8R8G8B8 (잠글 수 없습니다)|**하드웨어 업데이트**|소프트웨어 업데이트|소프트웨어 업데이트|소프트웨어 업데이트|  
|D3DFMT_A8R8G8B8 (잠금)|**하드웨어 업데이트**|소프트웨어 업데이트|**하드웨어 업데이트**|소프트웨어 업데이트|  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Interop.D3DImage>
- [WPF 및 Direct3D9 상호 운용성](wpf-and-direct3d9-interoperation.md)
- [연습: WPF에서 호스팅할 Direct3D9 콘텐츠 만들기](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)
- [연습: WPF에서 Direct3D9 콘텐츠 호스팅](walkthrough-hosting-direct3d9-content-in-wpf.md)

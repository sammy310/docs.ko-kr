---
title: ClearType 레지스트리 설정
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: bedd99fcf9b4ca1d10b4c24d7cff9de320e6fd12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186170"
---
# <a name="cleartype-registry-settings"></a>ClearType 레지스트리 설정
이 항목에서는 WPF 응용 프로그램에서 사용하는 Microsoft ClearType 레지스트리 설정에 대한 개요를 제공합니다.  

<a name="overview"></a>
## <a name="technology-overview"></a>기술 개요  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]디스플레이 장치에 텍스트를 렌더링하는 응용 프로그램은 ClearType 기능을 사용하여 향상된 읽기 환경을 제공합니다. ClearType은 노트북 화면, 포켓 PC 화면 및 평면 패널 모니터와 같은 기존 LCD(액정 디스플레이)에서 텍스트의 가독성을 향상시키는 Microsoft에서 개발한 소프트웨어 기술입니다. ClearType은 LCD 화면의 모든 픽셀에서 개별 세로 색상 스트라이프 요소에 액세스하여 작동합니다. ClearType에 대한 자세한 내용은 [ClearType 개요를](cleartype-overview.md)참조하십시오.  
  
 ClearType으로 렌더링된 텍스트는 다양한 디스플레이 장치에서 볼 때 크게 다르게 나타날 수 있습니다. 예를 들어 소수의 모니터는 일반적인 빨간색, 녹색, 파란색(RGB) 순서가 아닌 파란색, 녹색, 빨간색 순서로 색상 스트라이프 요소를 구현합니다.  
  
 ClearType으로 렌더링된 텍스트는 색상 민감도가 다양한 개인이 볼 때 크게 다르게 나타날 수도 있습니다. 어떤 사람은 다른 사람보다 미묘한 색의 차이를 더 잘 감지할 수 있습니다.  
  
 이러한 각 경우에 ClearType 기능은 각 개인에게 최상의 읽기 환경을 제공하기 위해 수정해야 합니다.  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a>레지스트리 설정  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType 기능을 제어하기 위한 네 가지 레지스트리 설정을 지정합니다.  
  
|설정|Description|  
|-------------|-----------------|  
|클리어 타입 수준|ClearType 색상 선명도에 대해 설명합니다.|  
|감마 수준|디스플레이 디바이스의 픽셀 색 구성 요소 수준을 설명합니다.|  
|픽셀 구조체|디스플레이 디바이스의 픽셀 배치를 설명합니다.|  
|텍스트 대비 수준|표시되는 텍스트의 대비 수준을 설명합니다.|  
  
 이러한 설정은 식별된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType 레지스트리 설정을 참조하는 방법을 알고 있는 외부 구성 유틸리티에서 액세스할 수 있습니다. 이러한 설정은 Windows 레지스트리 편집기에서 직접 값에 액세스하여 만들거나 수정할 수도 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType 레지스트리 설정이 설정되지 않은 경우(기본 상태인 경우) [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 글꼴 스무딩 설정에 대한 Windows 시스템 매개 변수 정보를 쿼리합니다.  
  
> [!NOTE]
> 표시 장치 이름 열거에 대한 자세한 `SystemParametersInfo`내용은 Win32 기능을 참조하십시오.  
  
<a name="ClearType_level"></a>
## <a name="cleartype-level"></a>ClearType 수준  
 ClearType 수준을 사용하면 개인의 색상 민감도와 인식에 따라 텍스트 렌더링을 조정할 수 있습니다. 일부 개인의 경우 ClearType을 가장 높은 수준에서 사용하는 텍스트 렌더링이 최상의 읽기 환경을 생성하지 못합니다.  
  
 ClearType 수준은 0에서 100까지의 정수 값입니다. 기본 수준은 100이며, 이는 ClearType이 디스플레이 장치의 색상 스트라이프 요소의 최대 기능을 사용한다는 것을 의미합니다. 그러나 ClearType 수준이 0이면 텍스트를 회색 축척으로 렌더링합니다. ClearType 수준을 0에서 100 사이로 설정하면 개인의 색상 감도에 적합한 중간 레벨을 만들 수 있습니다.  
  
### <a name="registry-setting"></a>레지스트리 설정  
 ClearType 수준에 대한 레지스트리 설정 위치는 특정 디스플레이 장치 이름에 해당하는 개별 사용자 설정입니다.  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 사용자의 각 표시 장치 이름에 `ClearTypeLevel` 대해 DWORD 값이 정의됩니다. 다음 스크린샷은 ClearType 수준에 대한 레지스트리 편집기 설정을 보여 주며 있습니다.  
  
 ![레지스트리 편집기에서 ClearType 설정을 입력합니다.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]응용 프로그램은 ClearType을 사용하거나 받지 않고 두 모드 중 하나에서 텍스트를 렌더링합니다. ClearType 없이 텍스트를 렌더링하는 경우 회색 축척 렌더링이라고 합니다.  
  
<a name="gamma_level"></a>
## <a name="gamma-level"></a>감마 수준  
 감마 수준은 픽셀 값과 광도 사이의 비선형 관계를 가리킵니다. 감마 수준 설정은 디스플레이 디바이스의 물리적 특성과 일치해야 합니다. 그렇지 않으면 렌더링된 출력에서 왜곡이 발생할 수 있습니다. 예를 들어 텍스트가 너무 넓거나 너무 좁아 보이거나 문자 표시의 세로 줄기 가장자리에 색상 가장자리가 나타날 수 있습니다.  
  
 감마 수준은 1,000에서 2,200까지의 정수 값입니다. 기본 수준은 1,900입니다.  
  
### <a name="registry-setting"></a>레지스트리 설정  
 감마 수준에 대한 레지스트리 설정 위치는 특정 디스플레이 디바이스 이름에 해당하는 로컬 컴퓨터 설정입니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 사용자의 각 표시 장치 이름에 `GammaLevel` 대해 DWORD 값이 정의됩니다. 다음 스크린샷에서는 감마 수준에 대한 레지스트리 편집기 설정을 보여 줍니다.  
  
 ![레지스트리 편집기에서 ClearType 감마 수준 설정](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>
## <a name="pixel-structure"></a>픽셀 구조체  
 픽셀 구조체는 디스플레이 디바이스를 구성하는 픽셀 형식을 설명합니다. 픽셀 구조체는 다음 세 가지 형식 중 하나로 정의됩니다.  
  
|Type|값|Description|  
|----------|-----------|-----------------|  
|플랫|0|디스플레이 디바이스에는 픽셀 구조체가 없습니다. 즉 각 색의 광원이 픽셀 영역에서 고르게 분산되며, 이를 회색조 렌더링이라고 합니다. 이 형식은 표준 디스플레이 디바이스에서 작동하는 방법입니다. ClearType은 렌더링된 텍스트에 적용되지 않습니다.|  
|RGB|1|디스플레이 디바이스에는 빨강, 녹색 및 파랑 순서의 3개 스트라이프로 구성되는 픽셀이 있습니다. ClearType은 렌더링된 텍스트에 적용됩니다.|  
|BGR|2|디스플레이 디바이스에는 파랑, 녹색 및 빨강 순서의 3개 스트라이프로 구성되는 픽셀이 있습니다. ClearType은 렌더링된 텍스트에 적용됩니다. 색의 순서가 RGB 형식과는 반대입니다.|  
  
 픽셀 구조체는 0에서 2까지의 정수 값에 해당합니다. 기본 수준은 플랫 픽셀 구조체를 나타내는 0입니다.  
  
> [!NOTE]
> 표시 장치 이름 열거에 대한 자세한 `EnumDisplayDevices`내용은 Win32 기능을 참조하십시오.  
  
### <a name="registry-setting"></a>레지스트리 설정  
 픽셀 구조체에 대한 레지스트리 설정 위치는 특정 디스플레이 디바이스 이름에 해당하는 로컬 컴퓨터 설정입니다.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 사용자의 각 표시 장치 이름에 `PixelStructure` 대해 DWORD 값이 정의됩니다. 다음 스크린샷에서는 픽셀 구조체에 대한 레지스트리 편집기 설정을 보여 줍니다.  
  
 ![레지스트리 편집기에서 ClearType 감마 수준 설정](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>
## <a name="text-contrast-level"></a>텍스트 대비 수준  
 텍스트 대비 수준을 사용하면 문자 모양의 획 너비를 기준으로 텍스트 렌더링을 조정할 수 있습니다. 텍스트 대비 수준은 0에서 6까지의 정수 값이며, 정수 값이 클수록 획이 넓어집니다. 기본 수준은 1입니다.  
  
### <a name="registry-setting"></a>레지스트리 설정  
 텍스트 대비 수준에 대한 레지스트리 설정 위치는 특정 디스플레이 디바이스 이름에 해당하는 개별 사용자 설정입니다.  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 사용자의 각 표시 장치 이름에 `TextContrastLevel` 대해 DWORD 값이 정의됩니다. 다음 스크린샷에서는 텍스트 대조 수준에 대한 레지스트리 편집기 설정을 보여 줍니다.  
  
 ![레지스트리 편집기에서 ClearType 설정을 입력합니다.](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a>참고 항목

- [ClearType 개요](cleartype-overview.md)
- [ClearType 앤티 앨리어싱](/windows/desktop/gdi/cleartype-antialiasing)

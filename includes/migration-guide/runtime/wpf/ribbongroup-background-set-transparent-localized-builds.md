---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802565"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>RibbonGroup 배경은 지역화된 빌드에서 투명하게 설정됩니다.

|   |   |
|---|---|
|세부 정보|지역화된 빌드의 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> 배경은 항상 투명한 브러시로 그려져서 UI 환경이 저하되었습니다. 이 문제는 .NET Framework 4.7 WPF 픽스에서 올바른 브러시가 선택되도록 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>의 지역화된 리소스를 업데이트하여 해결되었습니다.|
|제안 해결 방법|NET Framework 4.7로 업그레이드|
|범위|가장자리|
|Version|4.6.2|
|형식|런타임|

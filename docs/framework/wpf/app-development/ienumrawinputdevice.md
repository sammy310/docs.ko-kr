---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 04caca0c580d26fde7fc9a3e3a11b7a8fed26d65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225523"
---
# <a name="ienumrawinputdevice"></a>IEnumRAWINPUTDEVICE
이 인터페이스는 원시 입력 장치를 열거하며 PresentationHost.exe에서만 사용됩니다.  
  
> [!NOTE]
>  이 API는 로컬 클라이언트 컴퓨터에서만 사용할 수 있도록 지원됩니다.  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md)|열거자 목록에서 다음 `celt` 요소(즉, RAWINPUTDEVICE 구조체)를 열거하고 `rgelt`의 실제 열거된 요소 수와 함께 `pceltFetched`에 반환합니다.|  
|[IEnumRAWINPUTDEVIC:Skip](ienumrawinputdevic-skip.md)|다음을 건너뛰도록 열거자에 지시 `celt` 열거형의 요소를 다음에 호출할 수 있도록 [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) 이러한 요소를 반환 하지 것입니다.|  
|[IEnumRAWINPUTDEVIC:Reset](ienumrawinputdevic-reset.md)|열거형 시퀀스를 시작 부분으로 다시 설정합니다.|  
|[IEnumRAWINPUTDEVIC:Clone](ienumrawinputdevic-clone.md)|현재 열거자와 동일한 상태인 다른 원시 입력 장치 열거자를 만들어 동일한 목록을 반복합니다.|  
  
## <a name="see-also"></a>참고자료

- [원시 입력 정보](/windows/desktop/inputdev/about-raw-input)

---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 05867af48b64cd1898b13fa055859c8cc0367c8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949580"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
다음 열거 `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 구조에 반환 되는 열거자의 목록에서 `rgelt` 실제 열거 된 요소 수와 함께 `pceltFetched`입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a>매개 변수  
 `celt`  
  
 [in] 수가 [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 에서 반환 된 `rgelt`합니다.  
  
 `rgelt`  
  
 [out] 열거된 RAWINPUTDEVICE 구조체를 수신할 celt 크기(또는 더 큰)의 배열입니다.  
  
 `pceltFetched`  
  
 [out] `rgelt`에 실제로 제공된 요소 수에 대한 포인터입니다. `NULL`가 1이면 호출자가 `rgelt`을 전달할 수 있습니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 HRESULT: 제공 된 요소 수가 S_OK `celt`; 그렇지 않으면 S_FALSE입니다.

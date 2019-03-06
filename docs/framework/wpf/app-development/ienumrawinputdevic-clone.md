---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: a4c5e7db813089d1dd138416ac54dd4be467b87b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355021"
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
현재 열거자와 동일한 상태인 다른 원시 입력 장치 열거자를 만들어 동일한 목록을 반복합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppenum`  
  
 [out] 수신 하는 출력 변수의 주소는 [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) 인터페이스 포인터입니다. 메서드가 성공 하면이 출력 변수 값 정의 되지 않습니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 HRESULT: 이 메서드는 표준 반환 값인 E_INVALIDARG, E_OUTOFMEMORY 및 E_UNEXPECTED를 지원합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 사용 하면 나중에 해당 지점에 반환 하기 위해 한 지점을 열거형 시퀀스에서 기록 하 합니다. 호출자는 첫 번째 열거자에서 별도로이 새 열거자를 해제 해야 합니다.

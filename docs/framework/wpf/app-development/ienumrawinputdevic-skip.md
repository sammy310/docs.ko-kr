---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: fadf7b5526598f446eb7e49640bf4d43ec7395bf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354520"
---
# <a name="ienumrawinputdevicskip"></a>IEnumRAWINPUTDEVIC:Skip
다음을 건너뛰도록 열거자에 지시 `celt` 열거형의 요소를 다음에 호출할 수 있도록 [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) 이러한 요소를 반환 하지 것입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
  
 [in] 건너뛸 요소 수입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 HRESULT: 제공 된 요소 수가 S_OK `celt`; 그렇지 않으면 S_FALSE입니다.

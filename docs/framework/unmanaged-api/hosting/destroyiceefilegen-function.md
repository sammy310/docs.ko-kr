---
description: '자세히 알아보기: DestroyICeeFileGen 함수'
title: DestroyICeeFileGen 함수
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: 14ae990999247b90f16b10115dea3408b965a04a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785655"
---
# <a name="destroyiceefilegen-function"></a>DestroyICeeFileGen 함수

[ICeeFileGen](iceefilegen-class.md) 개체를 소멸 시킵니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ceeFileGen`  
 진행 `ICeeFileGen` 제거할 개체입니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 표준 COM 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  

 `DestroyICeeFileGen``ICeeFileGen` [CreateICeeFileGen](createiceefilegen-function.md) 함수에서 만든 개체를 제거 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ICeeFileGen  
  
 **라이브러리:** MSCorPE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)

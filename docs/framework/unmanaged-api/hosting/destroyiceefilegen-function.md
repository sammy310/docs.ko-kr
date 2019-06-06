---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: daf674c0340998c0fd518e0f1af721bbe9ff653c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490475"
---
# <a name="destroyiceefilegen-function"></a>DestroyICeeFileGen 함수
제거는 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) 개체입니다.  
  
 .NET Framework 4에서이 함수에 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ceeFileGen`  
 [in] `ICeeFileGen` 소멸 시킬 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 표준 COM 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 `DestroyICeeFileGen` 제거 된 `ICeeFileGen` 하 여 만든 개체를 [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** ICeeFileGen.h  
  
 **라이브러리:** MSCorPE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

---
description: '자세히 알아보기: CreateICeeFileGen 함수'
title: CreateICeeFileGen 함수
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 10aefaad4dd1173e4ef55f727371bab508e2d40c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716932"
---
# <a name="createiceefilegen-function"></a>CreateICeeFileGen 함수

[ICeeFileGen](iceefilegen-class.md) 개체를 만듭니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ceeFileGen`  
 제한이 새 개체의 주소에 대 한 포인터 `ICeeFileGen` 입니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 표준 COM 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  

 `ICeeFileGen`개체는 CLR (공용 언어 런타임) PE (이식 가능한 실행) 파일을 만드는 데 사용 됩니다.  
  
 완료 되 면 [DestroyICeeFileGen](destroyiceefilegen-function.md) 함수를 호출 하 여 개체를 삭제 `ICeeFileGen` 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ICeeFileGen  
  
 **라이브러리:** MSCorPE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)

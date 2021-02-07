---
description: '자세히 알아보기: IAssemblyName:: GetName 메서드'
title: IAssemblyName::GetName 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
ms.openlocfilehash: 04cd6258c2fc60c9fc40e1e4b731e5c04a8d3112
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760747"
---
# <a name="iassemblynamegetname-method"></a>IAssemblyName::GetName 메서드

이 [IAssemblyName](iassemblyname-interface.md) 개체가 참조 하는 어셈블리의 단순한 암호화 되지 않은 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `lpcwBuffer`  
 [in, out] `pwzName` Null 종결자 문자를 포함 하는 와이드 문자 단위의 크기입니다.  
  
 `pwzName`  
 제한이 참조 된 어셈블리의 이름을 저장할 버퍼입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyName 인터페이스](iassemblyname-interface.md)

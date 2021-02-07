---
description: '자세히 알아보기: IAssemblyName:: GetProperty 메서드'
title: IAssemblyName::GetProperty 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
ms.openlocfilehash: 66528bb54e1cb4adbba8fa87088065bc40c2ee15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760734"
---
# <a name="iassemblynamegetproperty-method"></a>IAssemblyName::GetProperty 메서드

지정 된 속성 식별자가 참조 하는 속성에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `PropertyId`  
 진행 요청 된 속성에 대 한 고유 식별자입니다.  
  
 `pvProperty`  
 제한이 반환 된 속성 데이터입니다.  
  
 `pcbProperty`  
 [in, out] 의 크기 (바이트)입니다 `pvProperty` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyName 인터페이스](iassemblyname-interface.md)

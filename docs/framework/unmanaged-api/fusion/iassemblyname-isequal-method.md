---
description: '자세히 알아보기: IAssemblyName:: IsEqual 메서드'
title: IAssemblyName::IsEqual 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.IsEqual
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::IsEqual
helpviewer_keywords:
- IsEqual method [.NET Framework fusion]
- IAssemblyName::IsEqual method [.NET Framework fusion]
ms.assetid: 6dfc220f-d0d4-45b3-bfce-5829f817766f
topic_type:
- apiref
ms.openlocfilehash: f1bb0e26a217354e904ff79b397771d727a7a661
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760691"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual 메서드

지정 된 [](iassemblyname-interface.md) `IAssemblyName` 비교 플래그에 따라 지정 된 IAssemblyName 개체가이와 같은지 여부를 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pName`  
 진행 `IAssemblyName` 이와 비교할 개체 `IAssemblyName` 입니다.  
  
 `dwCmpFlags`  
 진행 비교에 영향을 주는 [ASM_CMP_FLAGS](asm-cmp-flags-enumeration.md) 값의 비트 조합입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.Net Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyName 인터페이스](iassemblyname-interface.md)
- [Fusion 열거형](fusion-enumerations.md)

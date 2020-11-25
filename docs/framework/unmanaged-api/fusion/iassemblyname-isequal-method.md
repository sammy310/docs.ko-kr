---
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
ms.openlocfilehash: 0fabf8159c2626d4e1716e3be60baaf1ec834032
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712991"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual 메서드

지정 된 [IAssemblyName](iassemblyname-interface.md) `IAssemblyName` 비교 플래그에 따라 지정 된 IAssemblyName 개체가이와 같은지 여부를 확인 합니다.  
  
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
  
## <a name="see-also"></a>참조

- [IAssemblyName 인터페이스](iassemblyname-interface.md)
- [Fusion 열거형](fusion-enumerations.md)

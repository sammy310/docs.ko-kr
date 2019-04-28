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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80402234d9374fa4f16e1f8bb315536a9bdfb2c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697214"
---
# <a name="iassemblynameisequal-method"></a>IAssemblyName::IsEqual 메서드
지정 된 결정 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 개체와 같으면이 `IAssemblyName`지정된 된 비교 플래그에 따라 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsEqual (  
    [in] IAssemblyName  *pName,  
    [in] DWORD          dwCmpFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pName`  
 [in] 합니다 `IAssemblyName` 비교 하는 개체 `IAssemblyName`합니다.  
  
 `dwCmpFlags`  
 [in] 비트 조합 [ASM_CMP_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cmp-flags-enumeration.md) 비교에 영향을 주는 값입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Fusion.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Fusion 열거형](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)

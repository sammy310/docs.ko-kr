---
title: IManagedObject::GetObjectIdentity 메서드
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
ms.openlocfilehash: 1b40ed8e107d30c22b4ade25d29376b1b74583d1
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842415"
---
# <a name="imanagedobjectgetobjectidentity-method"></a>IManagedObject::GetObjectIdentity 메서드
이 관리 되는 개체의 id를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pBSTRGUID`  
 제한이 개체가 있는 프로세스의 GUID에 대 한 포인터입니다.  
  
 `AppDomainID`  
 제한이 개체의 응용 프로그램 도메인 ID에 대 한 포인터입니다.  
  
 `pCCW`  
 제한이 COM 클래식 v-table에서 개체의 인덱스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 관리 되는 개체의 id는 프로세스 GUID, 응용 프로그램 도메인 ID 및 COM 클래식 v-table의 개체 인덱스를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IManagedObject 인터페이스](imanagedobject-interface.md)

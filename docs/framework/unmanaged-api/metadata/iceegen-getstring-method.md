---
title: ICeeGen::GetString 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: ada126b41f1c634f7d8daa58480406ac26f92377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177899"
---
# <a name="iceegengetstring-method"></a>ICeeGen::GetString 메서드
지정된 상대 가상 주소에 저장된 문자열을 가져옵니다.  
  
 이 메서드는 더 이상 사용되지 않으며 사용해서는 안 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `RVA`  
 【인】 반환할 문자열의 상대적인 가상 주소입니다.  
  
 `lpString`  
 【아웃】 반환된 문자열입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

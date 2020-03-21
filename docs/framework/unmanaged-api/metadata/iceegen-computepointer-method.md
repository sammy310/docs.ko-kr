---
title: ICeeGen::ComputePointer 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
ms.openlocfilehash: 9587bbe8f087fd9a51bba67492af1d5acb53ae4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176099"
---
# <a name="iceegencomputepointer-method"></a>ICeeGen::ComputePointer 메서드
지정된 코드 섹션에 대한 버퍼를 결정합니다.  
  
 이 메서드는 더 이상 사용되지 않으며 사용해서는 안 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `section`  
 【인】 버퍼를 반환할 코드 섹션입니다.  
  
 `RVA`  
 【인】 포인터를 얻을 메서드의 상대적인 가상 주소입니다.  
  
 `lpBuffer`  
 【아웃】 반환된 버퍼에 대한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

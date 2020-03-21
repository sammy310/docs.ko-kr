---
title: ICeeGen::GetSectionBlock 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: a494b1aaa762549528e92ab93d18929ef73eb8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176086"
---
# <a name="iceegengetsectionblock-method"></a>ICeeGen::GetSectionBlock 메서드
코드 베이스의 섹션 블록을 가져옵니다.  
  
 이 메서드는 더 이상 사용되지 않으며 사용해서는 안 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a>매개 변수  
 `section`  
 【인】 코드 베이스의 블록을 검색할 섹션입니다.  
  
 `len`  
 【인】 검색할 블록의 길이입니다.  
  
 `align`  
 【인】 블록의 첫 번째 바이트를 정렬하는 섹션의 시작 부분을 기준으로 하는 바이트입니다. 섹션 내의 블록 위치입니다.  
  
 `ppBytes`  
 【아웃】 검색된 블록의 주소를 수신하는 위치에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 다른 `GetSectionBlock` 방법으로 처리되지 않는 특별한 섹션 요구 사항이 있는 경우에만 호출합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

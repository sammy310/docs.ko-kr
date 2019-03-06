---
title: ICeeGen::TruncateSection 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69f536e6add43d664eba436e185275632dc0063a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479352"
---
# <a name="iceegentruncatesection-method"></a>ICeeGen::TruncateSection 메서드
지정 된 코드 섹션을 지정 된 길이로 자릅니다.  
  
 이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `section`  
 [in] 자를 섹션입니다.  
  
 `len`  
 [in] 섹션 truncate 할 바이트 길이입니다.  
  
## <a name="remarks"></a>설명  
 호출 `TruncateSection` 다른 메서드에서 처리 되지 않는 특수 섹션 요구 사항이 있는 경우에 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

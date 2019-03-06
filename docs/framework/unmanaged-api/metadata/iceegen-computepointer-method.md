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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5fb63d4fe1e736ca1ff0c729d8d83cfe092eaaf5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465532"
---
# <a name="iceegencomputepointer-method"></a>ICeeGen::ComputePointer 메서드
지정 된 코드 섹션에 대 한 버퍼를 결정합니다.  
  
 이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `section`  
 [in] 버퍼를 반환 하는 코드 섹션입니다.  
  
 `RVA`  
 [in] 에 대 한 포인터를 가져올 메서드의 상대 가상 주소입니다.  
  
 `lpBuffer`  
 [out] 반환 된 버퍼에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

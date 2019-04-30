---
title: ICeeGen::GetMethodBuffer 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0aea6185095a30aae9197c875aa9b9ac581d406
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044969"
---
# <a name="iceegengetmethodbuffer-method"></a>ICeeGen::GetMethodBuffer 메서드
지정된 된 상대 가상 주소에서 메서드에 대 한 적절 한 크기의 버퍼를 가져옵니다.  
  
 이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `RVA`  
 [in] 버퍼를 반환 하는 메서드의 상대 가상 주소입니다.  
  
 `lpBuffer`  
 [out] 반환 된 버퍼에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

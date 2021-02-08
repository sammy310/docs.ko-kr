---
description: '자세한 정보: ICeeGen:: TruncateSection 메서드'
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
ms.openlocfilehash: 074c7d7b4222b5b22f1d9b79169d531cd5544b1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784212"
---
# <a name="iceegentruncatesection-method"></a>ICeeGen::TruncateSection 메서드

지정 된 코드 섹션을 지정 된 길이로 자릅니다.  
  
 이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `section`  
 진행 잘라낼 섹션입니다.  
  
 `len`  
 진행 섹션을 잘라낼 길이 (바이트)입니다.  
  
## <a name="remarks"></a>설명  

 `TruncateSection`다른 메서드에서 처리 하지 않는 특별 한 섹션 요구 사항이 있는 경우에만를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICeeGen 인터페이스](iceegen-interface.md)

---
title: IHostFilter::MarkToken 메서드
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: b4db3b115517f0a146aeab469f091008d31efc86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718230"
---
# <a name="ihostfiltermarktoken-method"></a>IHostFilter::MarkToken 메서드

지정 된 메타 데이터 토큰이 처리 됨을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `tk`  
 진행 처리할 메타 데이터 토큰입니다.  
  
## <a name="remarks"></a>설명  

 일반적으로 토큰은 메타 데이터 범위에 있는 경우 처리 하도록 하려고 합니다. `MarkToken`메서드는 [IMetaDataEmit:: SetHandler](imetadataemit-sethandler-method.md) 메서드를 통해 메타 데이터 엔진에 전달 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 인터페이스](metadata-interfaces.md)
- [IHostFilter 인터페이스](ihostfilter-interface.md)

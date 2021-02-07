---
description: '자세히 알아보기: ICLRErrorReportingManager:: GetBucketParametersForCurrentException 메서드'
title: ICLRErrorReportingManager::GetBucketParametersForCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
ms.openlocfilehash: ba2b6cf1215e5d57f608a76a870b0a9c846ee8ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689406"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a>ICLRErrorReportingManager::GetBucketParametersForCurrentException 메서드

호출 스레드의 현재 예외에 대 한 Watson 버킷을 가져옵니다.  
  
 *버킷은* 동일한 코드 오류와 관련 된 오류 데이터의 컬렉션입니다. *Watson* 은 예외와 관련 된 데이터를 수집 및 분석 하기 위한 일련의 기술을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pParams`  
 제한이 예외에 대 한 오류 데이터를 포함 하는 [BucketParameters](bucketparameters-structure.md) 구조체에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRErrorReportingManager 인터페이스](iclrerrorreportingmanager-interface.md)

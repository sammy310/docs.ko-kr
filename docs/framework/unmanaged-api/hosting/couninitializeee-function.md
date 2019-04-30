---
title: CoUninitializeEE 함수
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b3712b4cb66facc105a03d7bfad235f09339056
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985740"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE 함수
`CoUninitializeEE` 사용 되지 않습니다 하 고 기능을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>설명  
 공용 언어 런타임 실행 엔진 프로세스에서 언로드할 수 없습니다. 실행 엔진 호출을 종료 하려면 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [CoInitializeEE 함수](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)

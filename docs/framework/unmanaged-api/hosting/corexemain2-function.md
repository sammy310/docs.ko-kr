---
description: _CorExeMain2 함수에 대해 자세히 알아보세요.
title: _CorExeMain2 함수
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
ms.openlocfilehash: 4629ea2f6c2ba13351c409bc382077eea926b507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717110"
---
# <a name="_corexemain2-function"></a>_CorExeMain2 함수

지정 된 메모리 매핑된 코드에서 진입점을 실행 합니다. 이 함수는 운영 체제 로더에 의해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pUnmappedPE`  
 진행 메모리 매핑된 코드에 대 한 포인터입니다.  
  
 `cUnmappedPE`  
 진행 포함할 수 있는 요소 수 `pUnmappedPE` 입니다.  
  
 `pImageNameIn`  
 진행 실행 가능 이미지의 이름에 대 한 포인터입니다.  
  
 `pLoadersFileName`  
 진행 로더 파일의 이름입니다.  
  
 `pCmdLine`  
 진행 명령줄 매개 변수 (있는 경우).  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 전역 정적 함수](../metadata/metadata-global-static-functions.md)

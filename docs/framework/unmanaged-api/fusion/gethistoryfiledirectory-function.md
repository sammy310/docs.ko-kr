---
description: '자세히 알아보기: GetHistoryFileDirectory 함수'
title: GetHistoryFileDirectory 함수
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
ms.openlocfilehash: 960bc75d69f4be6d1639e109d6327b5e65d3e129
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760968"
---
# <a name="gethistoryfiledirectory-function"></a>GetHistoryFileDirectory 함수

응용 프로그램 기록 디렉터리의 경로를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `wzDir`  
 제한이 응용 프로그램 기록 디렉터리의 경로를 저장할 버퍼입니다.  
  
 `pdwSize`  
 [in, out] 버퍼의 길이입니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 Winerror.h 파일에 정의 된 대로 다음 값 외에 표준 COM 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`wzDir` 또는 `pdwSize` 이 null 이거나 버전 문자열이 잘못 되었습니다.|  
  
## <a name="remarks"></a>설명  

 성공적으로 완료 되 면 `pdwSize` 인수는 경로 문자열의 길이로 설정 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **라이브러리:** Fusion.dll 및 Mscorwks.dll. Mscorwks.dll 대신 Fusion.dll를 사용 하 여 올바른 버전의 .NET Framework를 대상으로 하는지 확인 합니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [CreateHistoryReader 함수](createhistoryreader-function.md)
- [NukeDownloadedCache 함수](nukedownloadedcache-function.md)
- [Fusion 전역 정적 함수](fusion-global-static-functions.md)

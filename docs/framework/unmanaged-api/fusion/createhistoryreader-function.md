---
description: '자세히 알아보기: CreateHistoryReader 함수'
title: CreateHistoryReader 함수
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
ms.openlocfilehash: 0943f3d0f3322d34ed92c0a96b909e4d63ec5e7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761124"
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader 함수

지정 된 파일에 대 한 기록 판독기를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>매개 변수  

 `wzFilePath`  
 진행 파일 경로입니다.  
  
 `ppHistoryReader`  
 제한이 성공적으로 완료 되 면 기록 판독기에 대 한 포인터를 포함 합니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 Winerror.h에 정의 된 대로 표준 COM 오류 코드와 함께 다음 표에 설명 된 값을 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 성공적으로 완료 되었음을 나타냅니다.|  
|E_INVALIDARG|`wzFilePath`또는 `ppHistoryReader` 가 null 참조로 설정 됨을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **라이브러리:** Fusion.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [Fusion 전역 정적 함수](fusion-global-static-functions.md)

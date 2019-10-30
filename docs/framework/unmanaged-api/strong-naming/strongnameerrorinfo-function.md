---
title: StrongNameErrorInfo 함수
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
ms.openlocfilehash: dd83fc6a7f553b54cc2acd5e9a93d8d58747d75a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141706"
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo 함수
강력한 이름 함수 중 하나에 의해 발생하는 마지막 오류 코드를 가져옵니다.  
  
 이 함수는 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>반환 값  
 강력한 이름 함수 중 하나로 설정 된 마지막 COM 오류 코드입니다.  
  
## <a name="remarks"></a>주의  
 대부분의 강력한 이름 메서드는 간단한 `true` 또는 성공적으로 완료 되었음을 나타내는 `false` 반환 합니다. `StrongNameErrorInfo` 함수를 사용 하 여 강력한 이름 함수에 의해 생성 된 마지막 오류를 지정 하는 HRESULT를 검색 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** StrongName  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  

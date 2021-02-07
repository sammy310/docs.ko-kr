---
description: '자세히 알아보기: CoUninitializeEE 함수'
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
ms.openlocfilehash: e356135ea027bd52520eff9084ad2f7f09e1fe0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746167"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE 함수

`CoUninitializeEE` 는 사용 되지 않으며 기능을 제공 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>설명  

 프로세스에서 공용 언어 런타임 실행 엔진을 언로드할 수 없습니다. 실행 엔진을 종료 하려면 [Corexitprocess](corexitprocess-function.md)를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목

- [CoInitializeEE 함수](coinitializeee-function.md)
- [메타데이터 전역 정적 함수](../metadata/metadata-global-static-functions.md)

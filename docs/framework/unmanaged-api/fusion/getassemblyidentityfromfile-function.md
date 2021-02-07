---
description: '자세히 알아보기: GetAssemblyIdentityFromFile 함수'
title: GetAssemblyIdentityFromFile 함수
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 8832e03182a5652c938404c99115fa8059439d1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761039"
---
# <a name="getassemblyidentityfromfile-function"></a>GetAssemblyIdentityFromFile 함수

`IUnknown`어셈블리에서 지정 된 파일 경로의 지정 된을 사용 하 여 개체에 대 한 포인터를 가져옵니다 `IID` .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a>매개 변수  

 `pwzFilePath`  
 진행 요청 된 어셈블리에 대 한 올바른 경로입니다.  
  
 `riid`  
 진행 `IID` 반환할 인터페이스의입니다.  
  
 `ppIdentity`  
 제한이 반환 된 인터페이스 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IUnknown](/cpp/atl/iunknown)
- [Fusion 전역 정적 함수](fusion-global-static-functions.md)

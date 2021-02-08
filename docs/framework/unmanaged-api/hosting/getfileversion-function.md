---
description: '자세히 알아보기: GetFileVersion 함수'
title: GetFileVersion 함수
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
ms.openlocfilehash: 7de19484f2f8123d61eb94e6a5ae09f56a3b5541
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785304"
---
# <a name="getfileversion-function"></a>GetFileVersion 함수

지정 된 버퍼를 사용 하 여 지정 된 파일의 CLR (공용 언어 런타임) 버전 정보를 가져옵니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szFilename`  
 진행 검사할 파일의 경로입니다.  
  
 `szBuffer`  
 [in, out] 반환 되는 버전 정보에 할당 된 버퍼입니다.  
  
 `cchBuffer`  
 진행 의 크기 (와이드 문자)입니다 `szBuffer` .  
  
 `dwLength`  
 제한이 반환 된의 크기 (바이트)입니다 `szBuffer` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)

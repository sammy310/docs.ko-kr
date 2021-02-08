---
description: '자세히 알아보기: IDebugAutoAttach:: AutoAttach 메서드'
title: IDebugAutoAttach::AutoAttach 메서드
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
ms.openlocfilehash: 8abd35b1d94fc074d4dafe424c52c274b1de1541
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800359"
---
# <a name="idebugautoattachautoattach-method"></a>IDebugAutoAttach::AutoAttach 메서드

서버에서 호출 하는 디버거 자동 연결을 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `guidPort`  
 진행 항상로 설정 `GUID_NULL` 합니다.  
  
 `dwPid`  
 진행 일반적으로 함수를 사용 하 여 검색 되는 프로세스 ID `GetCurrentProcessId` 입니다.  
  
 `dwProgramType`  
 진행 프로그램 유형: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` 또는 `AUTOATTACH_PROGRAM_UNKNOWN`  
  
 `dwProgramId`  
 진행 프로그램 ID입니다.  
  
 `pszSessionId`  
 진행 디버그 동사에 의해 전달 된 문자열입니다.  
  
## <a name="return-value"></a>Return Value  

 메서드가 성공 하면 S_OK 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** DbgAutoAttach  
  
## <a name="see-also"></a>참고 항목

- [IDebugAutoAttach 인터페이스](idebugautoattach-interface.md)

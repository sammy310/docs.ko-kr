---
description: '자세히 알아보기: GetTypeLibInfo 함수'
title: GetTypeLibInfo 함수
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
ms.openlocfilehash: 61a830f3ce81345634da377f6fc815a307700e9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794470"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo 함수

[TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) 구조를 시험하여 지정된 형식 라이브러리에 대한 정보를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szFile`  
 진행 형식 라이브러리의 파일 이름입니다.  
  
 `pTypeLibID`  
 제한이 형식 라이브러리의 GUID입니다.  
  
 `pTypeLibLCID`  
 제한이 형식 라이브러리의 지역화 ID입니다.  
  
 `pTypeLibPlatform`  
 제한이 형식 라이브러리의 대상 운영 체제를 식별 하는 [syskind](/windows/win32/api/oaidl/ne-oaidl-syskind) 플래그입니다. 공통 값은 SYS_WIN32 및 SYS_WIN64입니다.  
  
 `pTypeLibMajorVer`  
 제한이 형식 라이브러리의 주 버전 번호입니다. 예를 들어 버전 *x. y* 의 경우 주 버전 번호는 *x* 입니다.  
  
 `pTypeLibMinorVer`  
 제한이 형식 라이브러리의 부 버전 번호입니다. 예를 들어 버전 *x. y* 의 경우 부 버전 번호는 *y* 입니다.  
  
## <a name="remarks"></a>설명  

 `GetTypeLibInfo`함수는 [Tlbexp.exe (형식 라이브러리 내보내기)](../../tools/tlbexp-exe-type-library-exporter.md)에서 호출 됩니다. 이 도구는 CLR (공용 언어 런타임) 어셈블리의 형식을 설명 하는 형식 라이브러리를 생성 합니다.  
  
 매개 변수가 null 인 경우이 함수는의를 반환 합니다 `HRESULT` `E_POINTER` . 그렇지 않으면 `S_OK`을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** TlbRef  
  
 **라이브러리:** TlbRef  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [Tlbexp 도우미 함수](index.md)
- [LoadTypeLibEx 함수](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

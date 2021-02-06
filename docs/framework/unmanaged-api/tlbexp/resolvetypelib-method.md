---
description: '자세히 알아보기: ResolveTypeLib 메서드'
title: ResolveTypeLib 메서드
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
ms.openlocfilehash: ca7f94f630479d30bb9129497b38bcf04e759e5d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646285"
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib 메서드

정규화 된 경로를 반환 하 여 형식 라이브러리의 단순 이름을 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a>매개 변수  

 `bstrSimpleName`  
 진행 형식 라이브러리의 단순한 이름을 포함 하는 [BSTR](/previous-versions/windows/desktop/automat/bstr) 입니다.  
  
 `tlbid`  
 진행 레지스트리의 형식 라이브러리에 할당 된 GUID입니다.  
  
 `lcid`  
 진행 형식 라이브러리의 지역화 ID입니다.  
  
 `wMajorVersion`  
 진행 형식 라이브러리의 주 버전 번호입니다. 예를 들어 버전 *x. y* 의 경우 주 버전 번호는 *x* 입니다.  
  
 `wMinorVersion`  
 진행 형식 라이브러리의 부 버전 번호입니다. 예를 들어 버전 *x. y* 의 경우 부 버전 번호는 *y* 입니다.  
  
 `syskind`  
 진행 운영 환경을 식별 하는 [Syskind](/windows/win32/api/oaidl/ne-oaidl-syskind) 플래그입니다. 공통 값은 SYS_WIN32 및 SYS_WIN64입니다.  
  
 `pbstrResolvedTlbName`  
 제한이 매개 변수에 이름이 지정 된 형식 라이브러리의 전체 경로를 포함 하는 [BSTR](/previous-versions/windows/desktop/automat/bstr) 에 대 한 포인터입니다 `bstrSimpleName` .  
  
## <a name="remarks"></a>설명  

 `ResolveTypeLib`메서드는 [Tlbexp.exe (형식 라이브러리 내보내기)](../../tools/tlbexp-exe-type-library-exporter.md) 를 처리 하는 동안 [LoadTypeLibWithResolver 함수](loadtypelibwithresolver-function.md) 에서 호출 됩니다.  
  
 이 인터페이스의 사용자 지정 구현은 매개 변수에서 이름이 인 형식 라이브러리의 전체 경로를 포함 하는 [BSTR](/previous-versions/windows/desktop/automat/bstr) 을 반환 해야 합니다 `bstrSimpleName` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** TlbRef, TlbRef  
  
 **라이브러리:** TlbRef  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [Tlbexp 도우미 함수](index.md)
- [LoadTypeLibEx](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)

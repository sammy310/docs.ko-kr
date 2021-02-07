---
description: '자세히 알아보기: ICLRRuntimeInfo:: GetVersionString 메서드'
title: ICLRRuntimeInfo::GetVersionString 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
ms.openlocfilehash: 1c7603f4e9bb1142c415ba9da7a05a52d2d5e776
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753876"
---
# <a name="iclrruntimeinfogetversionstring-method"></a>ICLRRuntimeInfo::GetVersionString 메서드

지정 된 [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스와 연결 된 CLR (공용 언어 런타임) 버전 정보를 가져옵니다.  
  
 이 메서드는 다음 함수를 대체 합니다.  
  
- [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)  
  
- [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pwzBuffer`  
 제한이 "V *A*. 형식의 .NET Framework 컴파일 버전입니다. *B*[.*X*] ". *A*, *B* 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다. *X* 는 선택 사항입니다. *X* 가 없는 경우에는 후행 기간이 없습니다.  
  
> [!NOTE]
> 이 매개 변수는 C:\Windows\Microsoft.NET\Framework. 아래에 표시 되는 .NET Framework 버전의 디렉터리 이름과 일치 해야 합니다.  
  
 예제 값은 "v v1.0.3705", "v 1.1.4322", "v 2.0.50727" 및 "v 4.0입니다. *x*", 여기서 *x* 는 설치 된 빌드 번호에 따라 다릅니다. "V" 접두사는 필수입니다.  
  
 `pchBuffer`  
 [in, out] `pwzBuffer` 버퍼 오버런을 방지 하기 위해의 크기를 지정 합니다. `pwzBuffer`가 이면 `null` 미리 할당을 `pchBuffer` 허용 하기 위해의 필요한 크기를 반환 `pwzBuffer` 합니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pwzBuffer` 또는 `pchBuffer`가 null입니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [호스팅](index.md)

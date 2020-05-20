---
title: _CorDllMain 함수
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: 3b2322f708afed08172f87e843c225aa9c60d9d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616608"
---
# <a name="_cordllmain-function"></a>\_CorDllMain 함수

CLR (공용 언어 런타임)을 초기화 하 고, DLL 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `hInst`  
 진행 로드 된 모듈의 인스턴스 핸들입니다.  
  
 `dwReason`  
 진행 DLL 진입점 함수가 호출 되는 이유를 나타냅니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다. DLL \_ PROCESS_ATTACH, dll \_ 스레드 \_ 연결, dll \_ 스레드 \_ 연결 또는 dll \_ 프로세스 \_ 분리 합니다. 이러한 값에 대 한 설명은 `DllMain` PLATFORM SDK의 설명서를 참조 하세요.  
  
 `lpReserved`  
 진행 사용 되지 않는.  
  
## <a name="return-value"></a>Return Value  
 이 메서드 `true` 는 성공에 대해를 반환 하 고 `false` 오류가 발생 하면를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 DLL 어셈블리에 대 한 운영 체제 로더에 의해 호출 됩니다. 실행 어셈블리의 경우 로더가 대신 [ \_ CorExeMain](corexemain-function.md) 함수를 호출 합니다.  
  
 운영 체제 로더는 DLL 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.  
  
`_CorDllMain`함수는 운영 체제 로더에서 직접 호출 됩니다.
  
 자세한 내용은 [ \_ corvalidateimage](corvalidateimage-function.md) 항목의 설명 섹션을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 전역 정적 함수](../metadata/metadata-global-static-functions.md)

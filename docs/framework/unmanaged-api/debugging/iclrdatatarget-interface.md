---
title: ICLRDataTarget 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: 30806394a8895084068acaec6f7d03c6b67bb14b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860570"
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget 인터페이스
CLR (공용 언어 런타임)의 대상 항목과 상호 작용 하기 위한 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|Description|  
|------------|-----------------|  
|[GetCurrentThreadID 메서드](iclrdatatarget-getcurrentthreadid-method.md)|현재 스레드에 대 한 운영 체제 식별자를 가져옵니다.|  
|[GetImageBase 메서드](iclrdatatarget-getimagebase-method.md)|지정 된 이미지에 대 한 기본 메모리 주소를 가져옵니다.|  
|[GetMachineType 메서드](iclrdatatarget-getmachinetype-method.md)|대상 프로세스에서 사용 하는 명령 집합의 종류에 대 한 식별자를 가져옵니다.|  
|[GetPointerSize 메서드](iclrdatatarget-getpointersize-method.md)|현재 대상에 대 한 포인터의 크기 (바이트)를 가져옵니다.|  
|[GetThreadContext 메서드](iclrdatatarget-getthreadcontext-method.md)|지정 된 식별자를 가진 스레드의 컨텍스트에 대 한 포인터를 가져옵니다.|  
|[GetTLSValue 메서드](iclrdatatarget-gettlsvalue-method.md)|지정 된 스레드에 대 한 지정 된 인덱스의 TLS (스레드 로컬 저장소) 값을 가져옵니다.|  
|[ReadVirtual 메서드](iclrdatatarget-readvirtual-method.md)|지정 된 가상 메모리 주소에서 지정 된 버퍼로 데이터를 읽습니다.|  
|[Request 메서드](iclrdatatarget-request-method.md)|구현에 정의 된 대로 작업을 요청 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.|  
|[SetThreadContext 메서드](iclrdatatarget-setthreadcontext-method.md)|대상 프로세스에서 지정 된 스레드의 현재 컨텍스트를 설정 합니다.|  
|[SetTLSValue 메서드](iclrdatatarget-settlsvalue-method.md)|대상 프로세스에서 지정 된 스레드의 TLS (스레드 로컬 저장소)에 값을 설정 합니다.|  
|[WriteVirtual 메서드](iclrdatatarget-writevirtual-method.md)|지정 된 버퍼의 데이터를 지정 된 가상 메모리 주소에 씁니다.|  
  
## <a name="remarks"></a>설명  
 API 클라이언트 (즉, 디버거)는 특정 대상 항목에 대해 적절 하 게이 인터페이스를 구현 해야 합니다. 예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRDataTarget2 인터페이스](iclrdatatarget2-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)

---
title: ICorProfilerCallback::RemotingClientReceivingReply 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
ms.openlocfilehash: f7a943627e2087e6b8c78ced9fc32824843d44fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175137"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a>ICorProfilerCallback::RemotingClientReceivingReply 메서드
원격 호출의 서버 측 부분이 완료되었고 클라이언트가 이제 응답을 수신하고 처리하려고 하는 프로파일러에 알린다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a>매개 변수  
 `pCookie`  
 【인】 ICorProfilerCallback에서 제공 하는 값에 해당 하는 [값::Remoting서버보낸다음](icorprofilercallback-remotingserversendingreply-method.md) 조건:  
  
- 원격 GUID 쿠키가 활성화되어 있습니다.  
  
- 채널이 메시지를 전송하는 데 성공합니다.  
  
- GUID 쿠키는 서버 측 프로세스에서 활성화됩니다.  
  
 이렇게 하면 원격 호출을 쉽게 페어링할 수 있습니다.  
  
 `fIsAsync`  
 【인】 호출이 비동기인 `true` 경우값입니다. 그렇지 `false`않으면 .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)

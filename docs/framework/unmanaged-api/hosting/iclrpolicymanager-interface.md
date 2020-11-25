---
title: ICLRPolicyManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 7092a1c792fee7f6173dcde211b8e807f6ab02a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725588"
---
# <a name="iclrpolicymanager-interface"></a>ICLRPolicyManager 인터페이스

호스트에서 오류 및 시간 제한이 발생 하는 경우 수행할 정책 작업을 지정할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[SetActionOnFailure 메서드](iclrpolicymanager-setactiononfailure-method.md)|지정 된 오류가 발생할 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.|  
|[SetActionOnTimeout 메서드](iclrpolicymanager-setactionontimeout-method.md)|지정 된 작업의 제한 시간이 초과 될 때 CLR에서 수행 해야 하는 정책 동작을 지정 합니다.|  
|[SetDefaultAction 메서드](iclrpolicymanager-setdefaultaction-method.md)|지정 된 작업이 발생 했을 때 CLR에서 수행 해야 하는 정책 동작을 지정 합니다.|  
|[SetTimeout 메서드](iclrpolicymanager-settimeout-method.md)|지정 된 작업에 대 한 시간 제한 값을 설정 합니다.|  
|[SetTimeoutAndAction 메서드](iclrpolicymanager-settimeoutandaction-method.md)|지정 된 작업에 대 한 시간 제한 값을 설정 하 고 작업이 발생 했을 때 CLR에서 수행 해야 하는 정책 동작을 지정 합니다.|  
|[SetUnhandledExceptionPolicy 메서드](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|처리 되지 않은 예외가 발생할 때 CLR의 동작을 지정 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [EClrFailure 열거형](eclrfailure-enumeration.md)
- [EClrOperation 열거형](eclroperation-enumeration.md)
- [EPolicyAction 열거형](epolicyaction-enumeration.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)

---
description: '자세히 알아보기: ICLRHostBindingPolicyManager 인터페이스'
title: ICLRHostBindingPolicyManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 07a18d622ff8d8483fe6dcb0242cb5f1ee284b14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789946"
---
# <a name="iclrhostbindingpolicymanager-interface"></a>ICLRHostBindingPolicyManager 인터페이스

호스트에서 현재 바인딩 정책을 평가 하 고 지정 된 어셈블리에 대 한 정책 변경 내용을 전달 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EvaluatePolicy 메서드](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|호스트를 대신 하 여 바인딩 정책을 평가 합니다.|  
|[ModifyApplicationPolicy 메서드](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|지정 된 어셈블리에 대 한 바인딩 정책을 수정 하 고 정책의 새 버전을 만듭니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRAssemblyIdentityManager 인터페이스](iclrassemblyidentitymanager-interface.md)
- [IHostAssemblyStore 인터페이스](ihostassemblystore-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)

---
description: '자세히 알아보기: ComCallUnmarshal Coclass'
title: ComCallUnmarshal Coclass
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
ms.openlocfilehash: 508c1183e2862a286e9db0390bc0348629a9db8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799839"
---
# <a name="comcallunmarshal-coclass"></a>ComCallUnmarshal Coclass

인터페이스 포인터의 마샬링을 관리 하기 위한 인터페이스를 제공 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|`IMarshal`|클라이언트 프로세스에서 프록시를 만들고, 초기화 하 고, 관리 하는 메서드를 제공 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 Coclass](hosting-coclasses.md)

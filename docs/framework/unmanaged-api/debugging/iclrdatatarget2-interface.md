---
description: '자세히 알아보기: ICLRDataTarget2 인터페이스'
title: ICLRDataTarget2 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
ms.openlocfilehash: 9ba6d11ea043d3b6ba85544b47e063f585854af8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794847"
---
# <a name="iclrdatatarget2-interface"></a>ICLRDataTarget2 인터페이스

데이터 액세스 서비스 계층에서 대상 프로세스의 가상 메모리 영역을 조작 하는 데 사용 하는 [ICLRDataTarget](iclrdatatarget-interface.md) 의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[AllocVirtual 메서드](iclrdatatarget2-allocvirtual-method.md)|대상 프로세스의 주소 공간에 메모리를 할당 합니다.|  
|[FreeVirtual 메서드](iclrdatatarget2-freevirtual-method.md)|대상 프로세스의 주소 공간에 이전에 할당 된 메모리를 해제 합니다.|  
  
## <a name="remarks"></a>설명  

 API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다. 예를 들어 활성 프로세스의 구현은 메모리 덤프의 구현과는 다릅니다. 대상에서 메모리 영역의 수정을 지원하지 않을 수도 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRDataTarget 인터페이스](iclrdatatarget-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)

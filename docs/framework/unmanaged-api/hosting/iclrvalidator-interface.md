---
description: '자세히 알아보기: ICLRValidator 인터페이스'
title: ICLRValidator 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: 72ff94915d35967b6a8a87b022789ca697f61711
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636756"
---
# <a name="iclrvalidator-interface"></a>ICLRValidator 인터페이스

PE (이식 가능한 실행) 이미지를 확인 하 고 유효성 검사 오류를 보고 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[FormatEventInfo 메서드](iclrvalidator-formateventinfo-method.md)|지정 된 유효성 검사 오류에 대 한 자세한 메시지를 가져옵니다.|  
|[Validate 메서드](iclrvalidator-validate-method.md)|지정 된 파일에서 이식 가능한 실행 파일이 나 MSIL (Microsoft 중간 언어)의 유효성을 검사 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** IValidator, IValidator. h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRErrorReportingManager 인터페이스](iclrerrorreportingmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [CLRRuntimeHost Coclass](clrruntimehost-coclass.md)

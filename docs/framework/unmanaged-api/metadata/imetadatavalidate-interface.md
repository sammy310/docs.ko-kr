---
title: IMetaDataValidate 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataValidate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate
helpviewer_keywords:
- IMetaDataValidate interface [.NET Framework metadata]
ms.assetid: db98608a-e85c-4f50-9d7b-5f57a426ddb6
topic_type:
- apiref
ms.openlocfilehash: 2dbd4559bad54aee69f6980e8baf6441480f482c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489722"
---
# <a name="imetadatavalidate-interface"></a>IMetaDataValidate 인터페이스
메타데이터 서명의 유효성을 검사할 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|방법|설명|  
|------------|-----------------|  
|[ValidateMetaData 메서드](imetadatavalidate-validatemetadata-method.md)|현재 메타데이터 범위에서 개체에 대한 메타데이터 서명의 유효성을 검사합니다.|  
|[ValidatorInit 메서드](imetadatavalidate-validatorinit-method.md)|현재 메타데이터 범위에서 모듈 형식을 지정하는 플래그를 설정하고 유효성 검사 오류에 대한 지정된 콜백 메서드를 등록합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 인터페이스](metadata-interfaces.md)

---
title: IIdentityAuthority 인터페이스
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 263dc0f9d686440aaa23e359c26db1b4d3d09b1e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375972"
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority 인터페이스

코드 개체에 대 한 id 키를 관리합니다.

## <a name="methods"></a>메서드

|메서드|설명|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|두 개의 지정 되었는지 여부를 나타내는 값을 가져옵니다 [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) 인스턴스는 서로 같습니다.|
|`IIdentityAuthority::AreReferencesEqual`|두 개의 지정 되었는지 여부를 나타내는 값을 가져옵니다 [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) 인스턴스는 서로 같습니다.|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|두 지정 된 문자열 정의 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.|
|`IIdentityAuthority::AreTextualReferencesEqual`|두 지정 된 문자열 참조 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.|
|`IIdentityAuthority::CreateDefinition`|새 포인터를 가져옵니다 `IDefinitionIdentity` 현재 범위에 있는 코드 개체를 나타내는 인스턴스입니다.|
|`IIdentityAuthority::CreateReference`|새 포인터를 가져옵니다 `IReferenceIdentity` 현재 범위에 있는 코드 개체를 나타내는 인스턴스입니다.|
|`IIdentityAuthority::DefinitionToText`|지정 된 형식의 문자열 버전을 가져옵니다 `IDefinitionIdentity`합니다.|
|`IIdentityAuthority::DefinitionToTextBuffer`|지정 된 문자열 버전을 사용 하 여 지정 된 와이드 문자 버퍼를 채웁니다 `IDefinitionIdentity`합니다.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|나타내는 값을 가져옵니다 여부를 지정 된 `IDefinitionIdentity` 고 `IReferenceIdentity` 인스턴스가 동일한 코드 개체를 참조 합니다.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|지정된 된 문자열이 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.|
|`IIdentityAuthority::GenerateDefinitionKey`|지정 된 문자열을 새로 만든된 키에 대 한 포인터를 가져옵니다 `IDefinitionIdentity`합니다.|
|`IIdentityAuthority::GenerateReferenceKey`|지정 된 문자열을 새로 만든된 키에 대 한 포인터를 가져옵니다 `IReferenceIdentity`합니다.|
|`IIdentityAuthority::HashDefinition`|지정 된 해시 값을 가져옵니다 `IDefinitionIdentity`합니다.|
|`IIdentityAuthority::HashReference`|지정 된 해시 값을 가져옵니다 `IReferenceIdentity`합니다.|
|`IIdentityAuthority::ReferenceToText`|지정 된 형식의 문자열 버전을 가져옵니다 `IReferenceIdentity`합니다.|
|`IIdentityAuthority::ReferenceToTextBuffer`|지정 된 문자열 버전을 사용 하 여 지정 된 와이드 문자 버퍼를 채웁니다 `IReferenceIdentity`합니다.|
|`IIdentityAuthority::TextToDefinition`|한 인터페이스 포인터를 가져옵니다는 `IDefinitionIdentity` 형식 지정 문자열로 지정 된 생성 합니다.|
|`IIdentityAuthority::TextToReference`|한 인터페이스 포인터를 가져옵니다는 `IReferenceIdentity` 형식 지정 문자열로 지정 된 생성 합니다.|

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

**헤더:** Isolation.h

**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>참고자료

- [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)

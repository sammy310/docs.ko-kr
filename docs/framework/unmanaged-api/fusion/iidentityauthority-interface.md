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
ms.openlocfilehash: 3e2d2335e37ced9139ea44092f10b19566894681
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127086"
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority 인터페이스

코드 개체에 대 한 id 키를 관리 합니다.

## <a name="methods"></a>메서드

|메서드|설명|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|지정 된 두 [Idefinitionidentity](idefinitionidentity-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.|
|`IIdentityAuthority::AreReferencesEqual`|지정 된 두 [IReferenceIdentity](ireferenceidentity-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|지정 된 두 문자열 정의 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.|
|`IIdentityAuthority::AreTextualReferencesEqual`|지정 된 두 문자열 참조 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.|
|`IIdentityAuthority::CreateDefinition`|현재 범위에 있는 코드 개체를 나타내는 새 `IDefinitionIdentity` 인스턴스에 대 한 포인터를 가져옵니다.|
|`IIdentityAuthority::CreateReference`|현재 범위에 있는 코드 개체를 나타내는 새 `IReferenceIdentity` 인스턴스에 대 한 포인터를 가져옵니다.|
|`IIdentityAuthority::DefinitionToText`|지정 된 `IDefinitionIdentity`의 형식이 지정 된 문자열 버전을 가져옵니다.|
|`IIdentityAuthority::DefinitionToTextBuffer`|지정 된 와이드 문자 버퍼를 지정 된 `IDefinitionIdentity`의 문자열 버전으로 채웁니다.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|지정 된 `IDefinitionIdentity`와 `IReferenceIdentity` 인스턴스가 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|지정 된 문자열이 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.|
|`IIdentityAuthority::GenerateDefinitionKey`|지정 된 `IDefinitionIdentity`에 대해 새로 만든 문자열 키에 대 한 포인터를 가져옵니다.|
|`IIdentityAuthority::GenerateReferenceKey`|지정 된 `IReferenceIdentity`에 대해 새로 만든 문자열 키에 대 한 포인터를 가져옵니다.|
|`IIdentityAuthority::HashDefinition`|지정 된 `IDefinitionIdentity`에 대 한 해시 값을 가져옵니다.|
|`IIdentityAuthority::HashReference`|지정 된 `IReferenceIdentity`에 대 한 해시 값을 가져옵니다.|
|`IIdentityAuthority::ReferenceToText`|지정 된 `IReferenceIdentity`의 형식이 지정 된 문자열 버전을 가져옵니다.|
|`IIdentityAuthority::ReferenceToTextBuffer`|지정 된 와이드 문자 버퍼를 지정 된 `IReferenceIdentity`의 문자열 버전으로 채웁니다.|
|`IIdentityAuthority::TextToDefinition`|지정 된 형식이 지정 된 문자열에서 생성 된 `IDefinitionIdentity` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.|
|`IIdentityAuthority::TextToReference`|지정 된 형식이 지정 된 문자열에서 생성 된 `IReferenceIdentity` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.|

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** 격리. h

**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>참조

- [Fusion 인터페이스](fusion-interfaces.md)

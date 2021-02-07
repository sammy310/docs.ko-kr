---
description: '다음에 대 한 자세한 정보: IAppIdAuthority 인터페이스'
title: IAppIdAuthority 인터페이스
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: 238885c7f080571b414511c24f9772dbc19b4683
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761007"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority 인터페이스

응용 프로그램 id 및 참조에 대 한 키를 생성 하 고 비교 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|지정 된 두 [Idefinitionappid](idefinitionappid-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다. IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달 하 여 해당 버전 정보를 무시할 수 있습니다.|  
|`IAppIdAuthority::AreReferencesEqual`|지정 된 두 [Ireferenceappid](ireferenceappid-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다. IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달 하 여 해당 버전 정보를 무시할 수 있습니다.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|지정 된 두 문자열 정의가 같은지 여부를 나타내는 값을 가져옵니다. IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달 하 여 해당 버전 정보를 무시할 수 있습니다.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|지정 된 두 문자열 참조가 같은지 여부를 나타내는 값을 가져옵니다. IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달 하 여 해당 버전 정보를 무시할 수 있습니다.|  
|`IAppIdAuthority::CreateDefinition`|`IDefinitionAppId`현재 범위에서 어셈블리를 나타내는 새로 생성 된 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.|  
|`IAppIdAuthority::CreateReference`|`IReferenceAppId`현재 범위에서 어셈블리를 나타내는 새로 만든에 대 한 인터페이스 포인터를 가져옵니다.|  
|`IAppIdAuthority::DefinitionToText`|지정 된 `IDefinitionAppId` 플래그 값을 사용 하 여 지정 된의 문자열 버전을 가져옵니다.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|지정 된와가 같은 어셈블리를 나타내는지 여부를 나타내는 값을 가져옵니다 `IDefinitionAppId` `IReferenceAppId` .|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|지정 된 정의 문자열과 참조 문자열이 동일한 어셈블리를 나타내는지 여부를 나타내는 값을 가져옵니다.|  
|`IAppIdAuthority::GenerateDefinitionKey`|지정 된 인스턴스를 나타내는 문자열 키를 가져옵니다 `IDefinitionAppId` .|  
|`IAppIdAuthority::GenerateReferenceKey`|지정 된 인스턴스를 나타내는 문자열 키를 가져옵니다 `IReferenceAppId` .|  
|`IAppIdAuthority::HashDefinition`|지정 된 인스턴스에 대 한 해시 키를 가져옵니다 `IDefinitionAppId` .|  
|`IAppIdAuthority::HashReference`|지정 된 인스턴스에 대 한 해시 키를 가져옵니다 `IReferenceAppId` .|  
|`IAppIdAuthority::ReferenceToText`|지정 된 `IReferenceAppId` 플래그 값을 사용 하 여 지정 된의 문자열 버전을 가져옵니다.|  
|`IAppIdAuthority::TextToDefinition`|`IDefinitionAppId`지정 된 문자열 키가 참조 하는 어셈블리를 나타내는 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.|  
|`IAppIdAuthority::TextToReference`|`IReferenceAppId`지정 된 문자열 키가 참조 하는 어셈블리를 나타내는 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [Fusion 인터페이스](fusion-interfaces.md)

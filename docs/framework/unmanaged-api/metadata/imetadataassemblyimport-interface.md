---
title: IMetaDataAssemblyImport 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: c556fe247754b363ece0c5dc60750068276ddcc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714759"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport 인터페이스

어셈블리 매니페스트에 액세스하여 이를 검사하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CloseEnum 메서드](imetadataassemblyimport-closeenum-method.md)|지정 된 열거자에 대 한 핸들을 해제 합니다.|  
|[EnumAssemblyRefs 메서드](imetadataassemblyimport-enumassemblyrefs-method.md)|`mdAssemblyRef`현재 메타 데이터 범위에서 어셈블리가 참조 하는 어셈블리의 토큰을 포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다.|  
|[EnumExportedTypes 메서드](imetadataassemblyimport-enumexportedtypes-method.md)|`mdExportedType`현재 메타 데이터 범위에서 어셈블리가 참조 하는 COM 형식의 토큰을 포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다.|  
|[EnumFiles 메서드](imetadataassemblyimport-enumfiles-method.md)|`mdFile`현재 메타 데이터 범위에서 어셈블리가 참조 하는 파일의 토큰을 포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다.|  
|[EnumManifestResources 메서드](imetadataassemblyimport-enummanifestresources-method.md)|`mdManifestResource`현재 메타 데이터 범위에서 어셈블리가 참조 하는 리소스의 토큰을 포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다.|  
|[FindAssembliesByName 메서드](imetadataassemblyimport-findassembliesbyname-method.md)|`mdAssemblyRef`지정 된 이름을 가진 어셈블리에 대 한 토큰의 배열을 가져옵니다.|  
|[FindExportedTypeByName 메서드](imetadataassemblyimport-findexportedtypebyname-method.md)|지정 된 `mdExportedType` 이름을 사용 하 여 COM 형식에 대 한 토큰을 가져옵니다.|  
|[FindManifestResourceByName 메서드](imetadataassemblyimport-findmanifestresourcebyname-method.md)|지정 된 `mdManifestResource` 이름의 리소스에 대 한 토큰을 가져옵니다.|  
|[GetAssemblyFromScope 메서드](imetadataassemblyimport-getassemblyfromscope-method.md)|현재 메타 데이터 범위에 있는 어셈블리에 대 한 토큰을 가져옵니다.|  
|[GetAssemblyProps 메서드](imetadataassemblyimport-getassemblyprops-method.md)|지정 된 어셈블리의 속성 설정을 가져옵니다.|  
|[GetAssemblyRefProps 메서드](imetadataassemblyimport-getassemblyrefprops-method.md)|지정 된 토큰의 속성 설정을 가져옵니다 `mdAssemblyRef` .|  
|[GetExportedTypeProps 메서드](imetadataassemblyimport-getexportedtypeprops-method.md)|지정 된 COM 형식의 속성 설정을 가져옵니다.|  
|[GetFileProps 메서드](imetadataassemblyimport-getfileprops-method.md)|지정 된 파일의 속성 설정을 가져옵니다.|  
|[GetManifestResourceProps 메서드](imetadataassemblyimport-getmanifestresourceprops-method.md)|지정 된 매니페스트 리소스의 속성 설정을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 인터페이스](metadata-interfaces.md)
- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)

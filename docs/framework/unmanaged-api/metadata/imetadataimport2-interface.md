---
title: IMetaDataImport2 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: 0fd7915ef46899bdce8312bc6e8a466167e26382
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429215"
---
# <a name="imetadataimport2-interface"></a>IMetaDataImport2 인터페이스
[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인터페이스를 확장 하 여 제네릭 형식으로 작업 하는 기능을 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumGenericParamConstraints 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|지정 된 토큰이 나타내는 제네릭 매개 변수와 연결 된 제네릭 매개 변수 제약 조건의 배열에 대 한 열거자를 가져옵니다.|  
|[EnumGenericParams 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|지정 된 TypeDef 또는 MethodDef 토큰과 연결 된 제네릭 매개 변수 토큰의 배열에 대 한 열거자를 가져옵니다.|  
|[EnumMethodSpecs 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|지정 된 MethodDef 또는 MemberRef 토큰과 연결 된 MethodSpec 토큰 배열의 열거자를 가져옵니다.|  
|[GetGenericParamConstraintProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|지정 된 제약 조건 토큰이 나타내는 제네릭 매개 변수 제약 조건과 연결 된 메타 데이터를 가져옵니다.|  
|[GetGenericParamProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|지정 된 토큰이 나타내는 제네릭 매개 변수와 연결 된 메타 데이터를 가져옵니다.|  
|[GetMethodSpecProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|지정 된 MethodSpec 토큰에서 참조 하는 메서드의 메타 데이터 서명을 가져옵니다.|  
|[GetPEKind 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|현재 메타 데이터 범위에 정의 된 PE (이식 가능한 실행) 파일 (일반적으로 DLL 또는 EXE 파일)에서 코드의 특성을 식별 하는 값을 가져옵니다.|  
|[GetVersionString 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|어셈블리를 빌드하는 데 사용 된 런타임의 버전 번호를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Reflection.PortableExecutableKinds>
- [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)

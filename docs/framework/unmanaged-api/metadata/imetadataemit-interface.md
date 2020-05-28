---
title: IMetaDataEmit 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit
helpviewer_keywords:
- IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type:
- apiref
ms.openlocfilehash: a2c2512abc28f0140fc261c5136c7e1255db96de
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009216"
---
# <a name="imetadataemit-interface"></a>IMetaDataEmit 인터페이스
현재 정의 된 범위에서 어셈블리에 대 한 메타 데이터를 만들고, 수정 하 고, 저장 하는 메서드를 제공 합니다. 메타 데이터는 메모리에 저장 되거나 디스크에 저장 될 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|Description|  
|------------|-----------------|  
|[ApplyEditAndContinue 메서드](imetadataemit-applyeditandcontinue-method.md)|지정 된의 변경 내용을 사용 하 여 현재 어셈블리 범위를 업데이트 합니다 `pImport` .|  
|[DefineCustomAttribute 메서드](imetadataemit-definecustomattribute-method.md)|지정 된 메타 데이터 시그니처를 사용 하 여 지정 된 개체에 연결 되는 사용자 지정 특성에 대 한 정의를 만들고 해당 사용자 지정 특성 정의에 대 한 토큰을 가져옵니다.|  
|[DefineEvent 메서드](imetadataemit-defineevent-method.md)|지정 된 메타 데이터 시그니처를 사용 하 여 이벤트에 대 한 정의를 만들고 해당 이벤트 정의에 대 한 토큰을 가져옵니다.|  
|[DefineField 메서드](imetadataemit-definefield-method.md)|지정 된 메타 데이터 시그니처를 사용 하 여 필드에 대 한 정의를 만들고 해당 필드 정의에 대 한 토큰을 가져옵니다.|  
|[DefineImportMember 메서드](imetadataemit-defineimportmember-method.md)|현재 범위 외부의 모듈에 정의 된 형식의 멤버에 대 한 정의를 만들고 해당 참조 정의에 대 한 토큰을 가져옵니다.|  
|[DefineImportType 메서드](imetadataemit-defineimporttype-method.md)|현재 범위 외부의 모듈에 정의 된 형식에 대 한 참조 정의를 만들고 해당 참조 정의에 대 한 토큰을 가져옵니다.|  
|[DefineMemberRef 메서드](imetadataemit-definememberref-method.md)|현재 범위 외부에 있는 모듈의 멤버에 대 한 참조에 대 한 정의를 만들고 해당 참조 정의에 대 한 토큰을 가져옵니다.|  
|[DefineMethod 메서드](imetadataemit-definemethod-method.md)|지정 된 서명을 사용 하 여 메서드에 대 한 정의를 만들고 해당 메서드 정의에 대 한 토큰을 반환 합니다.|  
|[DefineMethodImpl 메서드](imetadataemit-definemethodimpl-method.md)|인터페이스에서 상속 된 메서드의 구현에 대 한 정의를 만들고 해당 메서드 구현 정의에 대 한 토큰을 반환 합니다.|  
|[DefineModuleRef 메서드](imetadataemit-definemoduleref-method.md)|지정 된 이름을 사용 하 여 모듈에 대 한 메타 데이터 서명을 만듭니다.|  
|[DefineNestedType 메서드](imetadataemit-definenestedtype-method.md)|형식 정의의 메타 데이터 서명을 만들고 `mdTypeDef` 해당 형식에 대 한 토큰을 반환 합니다 .이 경우 정의 된 형식이에서 참조 하는 형식의 멤버 임을 추가로 지정 합니다 `tdEncloser` .|  
|[DefineParam 메서드](imetadataemit-defineparam-method.md)|지정 된 토큰이 참조 하는 메서드에 대해 지정 된 서명을 사용 하 여 매개 변수 정의를 만들고 해당 매개 변수 정의에 대 한 토큰을 가져옵니다.|  
|[DefinePermissionSet 메서드](imetadataemit-definepermissionset-method.md)|지정 된 메타 데이터 시그니처를 사용 하 여 권한 집합에 대 한 정의를 만들고 해당 권한 집합 정의에 대 한 토큰을 가져옵니다.|  
|[DefinePinvokeMap 메서드](imetadataemit-definepinvokemap-method.md)|지정 된 토큰이 참조 하는 메서드에 대 한 PInvoke 시그니처의 기능을 설정 합니다.|  
|[DefineProperty 메서드](imetadataemit-defineproperty-method.md)|지정 된 및 메서드 접근자를 사용 하 여 지정 된 형식에 대 한 속성 정의를 만들고 `get` `set` 해당 속성 정의에 대 한 토큰을 가져옵니다.|  
|[DefineSecurityAttributeSet 메서드](imetadataemit-definesecurityattributeset-method.md)|지정 된 토큰이 참조 하는 개체에 연결할 보안 권한 집합을 만듭니다.|  
|[DefineTypeDef 메서드](imetadataemit-definetypedef-method.md)|공용 언어 런타임 형식에 대 한 형식 정의를 만들고 해당 형식 정의에 대 한 메타 데이터 토큰을 가져옵니다.|  
|[DefineTypeRefByName 메서드](imetadataemit-definetyperefbyname-method.md)|현재 범위 밖의 다른 모듈에 정의 된 형식에 대 한 메타 데이터 토큰을 가져옵니다.|  
|[DefineUserString 메서드](imetadataemit-defineuserstring-method.md)|지정 된 리터럴 문자열에 대 한 메타 데이터 토큰을 가져옵니다.|  
|[DeleteClassLayout 메서드](imetadataemit-deleteclasslayout-method.md)|지정 된 토큰이 참조 하는 형식에 대 한 클래스 레이아웃 메타 데이터 서명을 소멸 시킵니다.|  
|[DeleteFieldMarshal 메서드](imetadataemit-deletefieldmarshal-method.md)|지정 된 토큰이 참조 하는 개체에 대 한 PInvoke 마샬링 메타 데이터 서명을 제거 합니다.|  
|[DeletePinvokeMap 메서드](imetadataemit-deletepinvokemap-method.md)|지정 된 토큰이 참조 하는 개체에 대 한 PInvoke 매핑 메타 데이터를 제거 합니다.|  
|[DeleteToken 메서드](imetadataemit-deletetoken-method.md)|현재 메타 데이터 범위에서 지정 된 토큰을 삭제 합니다.|  
|[GetSaveSize 메서드](imetadataemit-getsavesize-method.md)|현재 범위에 있는 어셈블리의 예상 이진 크기를 가져옵니다.|  
|[GetTokenFromSig 메서드](imetadataemit-gettokenfromsig-method.md)|지정 된 메타 데이터 시그니처의 토큰을 가져옵니다.|  
|[GetTokenFromTypeSpec 메서드](imetadataemit-gettokenfromtypespec-method.md)|지정 된 메타 데이터 서명을 사용 하 여 형식에 대 한 메타 데이터 토큰을 가져옵니다.|  
|[Merge 메서드](imetadataemit-merge-method.md)|병합할 범위 목록에 지정 된 가져온 범위를 추가 합니다.|  
|[MergeEnd 메서드](imetadataemit-mergeend-method.md)|하나 이상의 이전 호출로 지정 된 모든 메타 데이터 범위를 현재 범위로 병합 `IMetaDataEmit::Merge` 합니다.|  
|[Save 메서드](imetadataemit-save-method.md)|현재 범위에 있는 모든 메타 데이터를 지정 된 주소에 있는 파일에 저장 합니다.|  
|[SaveToMemory 메서드](imetadataemit-savetomemory-method.md)|현재 범위에 있는 모든 메타 데이터를 지정 된 메모리 영역에 저장 합니다.|  
|[SaveToStream 메서드](imetadataemit-savetostream-method.md)|현재 범위에 있는 모든 메타 데이터를 지정 된에 저장 `IStream` 합니다.|  
|[SetClassLayout 메서드](imetadataemit-setclasslayout-method.md)|에 대 한 이전 호출에서 정의한 형식의 클래스 레이아웃 서명을 설정 하거나 업데이트 `IMetaDataEmit::DefineTypeDef` 합니다.|  
|[SetCustomAttributeValue 메서드](imetadataemit-setcustomattributevalue-method.md)|에 대 한 이전 호출에서 정의한 사용자 지정 특성의 값을 설정 하거나 업데이트 `IMetaDataEmit::DefineCustomAttribute` 합니다.|  
|[SetEventProps 메서드](imetadataemit-seteventprops-method.md)|에 대 한 이전 호출에서 정의한 이벤트의 지정 된 기능을 설정 하거나 업데이트 `IMetaDataEmit::DefineEvent` 합니다.|  
|[SetFieldMarshal 메서드](imetadataemit-setfieldmarshal-method.md)|지정 된 토큰이 참조 하는 필드, 메서드 반환 또는 메서드 매개 변수에 대 한 PInvoke 마샬링 정보를 설정 합니다.|  
|[SetFieldProps 메서드](imetadataemit-setfieldprops-method.md)|지정 된 필드 토큰이 참조 하는 필드의 기본값을 설정 하거나 업데이트 합니다.|  
|[SetFieldRVA 메서드](imetadataemit-setfieldrva-method.md)|지정 된 토큰이 참조 하는 필드의 상대 가상 주소에 대 한 전역 변수 값을 설정 합니다.|  
|[SetHandler 메서드](imetadataemit-sethandler-method.md)|지정 된 포인터가 참조 하는 메서드를 `IUnknown` 토큰 다시 매핑에 대 한 알림 콜백으로 설정 합니다.|  
|[SetMethodImplFlags 메서드](imetadataemit-setmethodimplflags-method.md)|지정 된 토큰이 참조 하는 상속 된 메서드 구현의 메타 데이터 서명을 설정 하거나 업데이트 합니다.|  
|[SetMethodProps 메서드](imetadataemit-setmethodprops-method.md)|이전 호출에 의해 정의 된 메서드의 지정 된 상대 가상 주소에 저장 된 기능을 설정 하거나 업데이트 `IMetaDataEmit::DefineMethod` 합니다.|  
|[SetModuleProps 메서드](imetadataemit-setmoduleprops-method.md)|에 대 한 이전 호출로 정의 된 모듈에 대 한 참조를 업데이트 `IMetaDataEmit::DefineModuleRef` 합니다.|  
|[SetParamProps 메서드](imetadataemit-setparamprops-method.md)|에 대 한 이전 호출로 정의 된 메서드 매개 변수의 기능을 설정 하거나 변경 `IMetaDataEmit::DefineParam` 합니다.|  
|[SetParent 메서드](imetadataemit-setparent-method.md)|에 대 한 이전 호출에서 정의한 대로 지정 된 멤버를 `IMetaDataEmit::DefineMemberRef` 에 대 한 이전 호출로 정의 된 지정 된 형식의 멤버로 설정 합니다 `IMetaDataEmit::DefineTypeDef` .|  
|[SetPermissionSetProps 메서드](imetadataemit-setpermissionsetprops-method.md)|에 대 한 이전 호출로 정의 된 사용 권한 집합의 메타 데이터 서명 기능을 설정 하거나 업데이트 `IMetaDataEmit::DefinePermissionSet` 합니다.|  
|[SetPinvokeMap 메서드](imetadataemit-setpinvokemap-method.md)|에 대 한 이전 호출에서 정의한 대로 메서드 PInvoke 시그니처의 기능을 설정 하거나 변경 `IMetaDataEmit::DefinePinvokeMap` 합니다.|  
|[SetPropertyProps 메서드](imetadataemit-setpropertyprops-method.md)|에 대 한 이전 호출로 정의 된 속성에 대 한 메타 데이터에 저장 된 기능을 설정 합니다 `IMetaDataEmit::DefineProperty` .|  
|[SetRVA 메서드](imetadataemit-setrva-method.md)|지정 된 메서드의 상대 가상 주소를 설정 합니다.|  
|[SetTypeDefProps 메서드](imetadataemit-settypedefprops-method.md)|에 대 한 이전 호출로 정의 된 형식의 기능을 설정 `IMetaDataEmit::DefineTypeDef` 합니다.|  
|[TranslateSigWithScope 메서드](imetadataemit-translatesigwithscope-method.md)|어셈블리를 현재 범위로 가져오고 병합 된 범위에 대 한 새 메타 데이터 서명을 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 인터페이스](metadata-interfaces.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)

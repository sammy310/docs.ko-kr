---
title: IMetaDataEmit::DefineMethod 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177670"
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod 메서드
지정된 시그니처를 사용하여 메서드 또는 전역 함수에 대한 정의를 만들고 해당 메서드 정의에 토큰을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineMethod (
    [in]  mdTypeDef         td,
    [in]  LPCWSTR           szName,
    [in]  DWORD             dwMethodFlags,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [in]  ULONG             ulCodeRVA,
    [in]  DWORD             dwImplFlags,
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `td`  
 【인】 메서드의 상위 클래스 또는 상위 인터페이스의 `mdTypedef` 토큰입니다. 전역 `td` `mdTokenNil`함수를 정의하는 경우 을 설정합니다.  
  
 `szName`  
 【인】 유니코드의 멤버 이름입니다.  
  
 `dwMethodFlags`  
 【인】 메서드 또는 전역 함수의 특성을 지정하는 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형의 값입니다.  
  
 `pvSigBlob`  
 【인】 메서드 시그니처입니다. 서명은 제공된 대로 유지됩니다. 매개 변수에 대한 추가 정보를 지정해야 하는 경우 [IMetaDataEmit:SetParamProps 메서드를](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) 사용합니다.  
  
 `cbSigBlob`  
 【인】 의 바이트 `pvSigBlob`수입니다.  
  
 `ulCodeRVA`  
 【인】 코드의 주소입니다.  
  
 `dwImplFlags`  
 【인】 메서드의 구현 기능을 지정 하는 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 열거형의 값입니다.  
  
 `pmd`  
 【아웃】 멤버 토큰입니다.  
  
## <a name="remarks"></a>설명  
 메타데이터 API는 호출자가 매개 변수에 지정된 지정된 둘러싸는 클래스 또는 인터페이스에 대해 메서드를 내보내는 것과 동일한 순서로 메서드를 `td` 유지하도록 보장합니다.  
  
 사용 및 특정 `DefineMethod` 매개 변수 설정에 대한 추가 정보는 아래에 있습니다.  
  
## <a name="slots-in-the-v-table"></a>V테이블의 슬롯  
 런타임은 메서드 정의를 사용하여 v-테이블 슬롯을 설정합니다. COM 인터페이스 레이아웃을 사용하여 패리티를 보존하는 것과 같이 하나 이상의 슬롯을 건너뛰어야 하는 경우 더미 메서드는 v-table의 슬롯 또는 슬롯을 차지하도록 정의됩니다. `dwMethodFlags` [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형의 `mdRTSpecialName` 값으로 설정하고 이름을 다음과 같이 지정합니다.  
  
 _VtblGap\<*시퀀스수*>\<\_*카운트오브슬롯*>
  
 *여기서 SequenceNumber는* 메서드의 시퀀스 번호이며 *CountOfSlots는* v 테이블에서 건너뛸 슬롯 수입니다. *CountOfSlots를* 생략하면 1이 가정됩니다. 이러한 더미 메서드는 관리되는 코드또는 관리되지 않는 코드에서 호출할 수 없으며 관리되거나 관리되지 않는 코드에서 호출하려는 모든 시도는 예외를 생성합니다. 유일한 목적은 런타임이 COM 통합을 위해 생성하는 v-table의 공간을 차지합니다.  
  
## <a name="duplicate-methods"></a>중복 방법  
 중복 메서드를 정의해서는 안 됩니다. `DefineMethod` 즉, `td`에서 `wzName` `pvSig` 의 값 집합을 중복하여 호출해서는 안 됩니다. (이 세 매개 변수는 함께 메서드를 고유하게 정의합니다.) 그러나 메서드 정의 중 하나에 대해 `mdPrivateScope` `dwMethodFlags` 매개 변수의 비트를 설정하는 경우 중복 트리플을 사용할 수 있습니다. 비트는 `mdPrivateScope` 컴파일러가 이 메서드 정의에 대한 참조를 내제공하지 않음을 의미합니다.  
  
## <a name="method-implementation-information"></a>방법 구현 정보  
 메서드 구현에 대한 정보는 메서드가 선언될 때 알려져 있지 않은 경우가 많습니다. 따라서 을 호출할 `ulCodeRVA` `dwImplFlags` `DefineMethod`때 및 매개 변수에 값을 전달할 필요가 없습니다. 이 값은 나중에 [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) 또는 [IMetaDataEmemit::SetRVA를](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)통해 적절히 제공될 수 있습니다.  
  
 플랫폼 호출(PInvoke) 또는 COM interop 시나리오와 같은 일부 상황에서는 메서드 본문이 `ulCodeRVA` 제공되지 않으며 0으로 설정해야 합니다. 이러한 상황에서는 런타임에서 구현을 찾므로 메서드에 추상태그가 지정되어서는 안 됩니다.  
  
## <a name="defining-a-method-for-pinvoke"></a>PInvoke에 대한 방법 정의  
 PInvoke를 통해 호출되는 각 관리되지 않는 함수에 대해 대상 관리되지 않는 함수를 나타내는 관리되는 메서드를 정의해야 합니다. 관리되는 메서드를 정의하려면 PInvoke가 사용되는 방식에 따라 특정 값으로 설정된 일부 매개 변수와 함께 사용합니다. `DefineMethod`  
  
- True PInvoke - 관리되지 않는 DLL에 상주하는 외부 관리되지 않는 메서드를 호출합니다.  
  
- 로컬 PInvoke - 현재 관리되는 모듈에 포함된 기본 관리되지 않는 메서드를 호출합니다.  
  
 매개 변수 설정은 다음 표에 제공됩니다.  
  
|매개 변수|진정한 핀보크에 대한 값|로컬 PInvoke의 값|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||집합; `mdStatic` `mdSynchronized` 명확하고 `mdAbstract`.|  
|`pvSigBlob`|유효한 관리 되는 형식 매개 변수를 사용 하는 유효한 공통 언어 런타임 (CLR) 메서드 서명입니다.|유효한 관리 되는 형식 매개 변수를 사용 하는 유효한 CLR 메서드 서명입니다.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|`miCil` 및 `miManaged`를 설정합니다.|`miNative` 및 `miUnmanaged`를 설정합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

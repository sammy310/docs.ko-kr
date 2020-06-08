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
ms.openlocfilehash: fbf6ce8c8c9628b08872058a794fb0e005764ab1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501302"
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod 메서드
지정 된 서명을 사용 하 여 메서드 또는 전역 함수에 대 한 정의를 만들고 해당 메서드 정의에 대 한 토큰을 반환 합니다.  
  
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
 진행 `mdTypedef`메서드의 부모 클래스 또는 부모 인터페이스의 토큰입니다. `td` `mdTokenNil` 전역 함수를 정의 하는 경우로 설정 합니다.  
  
 `szName`  
 진행 유니코드로 된 멤버 이름입니다.  
  
 `dwMethodFlags`  
 진행 메서드 또는 전역 함수의 특성을 지정 하는 [CorMethodAttr](cormethodattr-enumeration.md) 열거형의 값입니다.  
  
 `pvSigBlob`  
 진행 메서드 시그니처입니다. 제공 된 대로 서명이 유지 됩니다. 매개 변수에 대 한 추가 정보를 지정 해야 하는 경우 [IMetaDataEmit:: SetParamProps](imetadataemit-setparamprops-method.md) 메서드를 사용 합니다.  
  
 `cbSigBlob`  
 진행 의 바이트 수 `pvSigBlob` 입니다.  
  
 `ulCodeRVA`  
 진행 코드의 주소입니다.  
  
 `dwImplFlags`  
 진행 메서드의 구현 기능을 지정 하는 [Cormethodimpl](cormethodimpl-enumeration.md) 열거형의 값입니다.  
  
 `pmd`  
 제한이 멤버 토큰입니다.  
  
## <a name="remarks"></a>설명  
 메타 데이터 API는 호출자가 매개 변수에 지정 된 지정 된 바깥쪽 클래스 또는 인터페이스에 대해 메서드를 내보내는 것과 동일한 순서로 메서드를 유지 하도록 보장 합니다 `td` .  
  
 `DefineMethod`및 특정 매개 변수 설정 사용에 대 한 추가 정보는 아래에 제공 됩니다.  
  
## <a name="slots-in-the-v-table"></a>V 테이블의 슬롯  
 런타임은 메서드 정의를 사용 하 여 v 테이블 슬롯을 설정 합니다. COM 인터페이스 레이아웃을 사용 하 여 패리티를 유지 하는 등 하나 이상의 슬롯을 건너뛰어야 하는 경우 더미 메서드는 v-table의 슬롯을 차지 하도록 정의 됩니다. 을 `dwMethodFlags` `mdRTSpecialName` [CorMethodAttr](cormethodattr-enumeration.md) 열거형의 값으로 설정 하 고 이름을 다음과 같이 지정 합니다.  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>
  
 여기서 *SequenceNumber* 는 메서드의 시퀀스 번호이 고 *CountOfSlots* 는 v 테이블에서 건너뛸 슬롯 수입니다. *CountOfSlots* 를 생략 하면 1이 가정 됩니다. 이러한 더미 메서드는 관리 코드 또는 비관리 코드에서 호출할 수 없으며 관리 코드 또는 비관리 코드에서 호출 하려고 하면 예외가 발생 합니다. 유일한 용도는 런타임에서 COM 통합을 위해 생성 하는 v-table의 공간을 차지 하는 것입니다.  
  
## <a name="duplicate-methods"></a>중복 메서드  
 중복 메서드를 정의 하면 안 됩니다. 즉,, `DefineMethod` `td` `wzName` 및 매개 변수에서 중복 값 집합을 사용 하 여를 호출 하면 안 됩니다 `pvSig` . 이 세 매개 변수는 메서드를 고유 하 게 정의 합니다. 그러나 메서드 정의 중 하나에 대해 `mdPrivateScope` 매개 변수에서 비트를 설정 하는 경우 중복 된 삼중을 사용할 수 있습니다 `dwMethodFlags` . 비트는 `mdPrivateScope` 컴파일러에서이 메서드 정의에 대 한 참조를 내보내지 않는다는 것을 의미 합니다.  
  
## <a name="method-implementation-information"></a>메서드 구현 정보  
 메서드 구현에 대 한 정보는 메서드가 선언 될 때 알려지지 않는 경우가 많습니다. 따라서를 `ulCodeRVA` `dwImplFlags` 호출할 때 및 매개 변수에 값을 전달할 필요가 없습니다 `DefineMethod` . 이러한 값은 나중에 [IMetaDataEmit:: SetMethodImplFlags](imetadataemit-setmethodimplflags-method.md) 또는 [IMetaDataEmit:: setrva](imetadataemit-setrva-method.md)를 통해 적절 하 게 제공할 수 있습니다.  
  
 플랫폼 호출 (PInvoke) 또는 COM interop 시나리오와 같은 경우에는 메서드 본문이 제공 되지 않으므로 `ulCodeRVA` 0으로 설정 해야 합니다. 이러한 경우 런타임이 구현을 찾기 때문에 메서드는 abstract로 태그를 지정 하면 안 됩니다.  
  
## <a name="defining-a-method-for-pinvoke"></a>PInvoke에 대 한 메서드 정의  
 PInvoke를 통해 호출 되는 관리 되지 않는 각 함수에 대해 대상 관리 되지 않는 함수를 나타내는 관리 되는 메서드를 정의 해야 합니다. 관리 되는 메서드를 정의 하려면 `DefineMethod` PInvoke를 사용 하는 방식에 따라 특정 값으로 설정 된 몇 가지 매개 변수를 사용 합니다.  
  
- True PInvoke-관리 되지 않는 DLL에 상주 하는 관리 되지 않는 외부 메서드를 호출 합니다.  
  
- 로컬 PInvoke-현재 관리 되는 모듈에 포함 된 관리 되지 않는 네이티브 메서드를 호출 합니다.  
  
 다음 표에서는 매개 변수 설정을 제공 합니다.  
  
|매개 변수|True PInvoke 값|로컬 PInvoke 값|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Set `mdStatic` , `mdSynchronized` 및을 선택 취소 `mdAbstract` 합니다.|  
|`pvSigBlob`|유효한 관리 되는 형식인 매개 변수가 포함 된 유효한 CLR (공용 언어 런타임) 메서드 시그니처입니다.|유효한 관리 되는 형식인 매개 변수가 포함 된 유효한 CLR 메서드 시그니처입니다.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|`miCil` 및 `miManaged`를 설정합니다.|`miNative` 및 `miUnmanaged`를 설정합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)

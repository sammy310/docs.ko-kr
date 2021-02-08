---
description: IMetaDataEmit::D efineProperty 메서드에 대해 자세히 알아보세요.
title: IMetaDataEmit::DefineProperty 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: c0c0b6009f8674a5edebf1c982e277f4ca5b185b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784034"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="2c605-103">IMetaDataEmit::DefineProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="2c605-103">IMetaDataEmit::DefineProperty Method</span></span>

<span data-ttu-id="2c605-104">지정 된 및 메서드 접근자를 사용 하 여 지정 된 형식에 대 한 속성 정의를 만들고 `get` `set` 해당 속성 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-104">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c605-105">구문</span><span class="sxs-lookup"><span data-stu-id="2c605-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c605-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c605-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="2c605-107">진행 속성이 정의 되는 클래스 또는 인터페이스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-107">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="2c605-108">진행 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-108">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="2c605-109">진행 속성 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-109">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="2c605-110">진행 속성 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-110">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="2c605-111">진행 의 바이트 수 `pvSig` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-111">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2c605-112">진행 속성의 기본값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-112">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2c605-113">진행 속성의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-113">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2c605-114">진행 의 (유니코드) 문자 수입니다 `pValue` .</span><span class="sxs-lookup"><span data-stu-id="2c605-114">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="2c605-115">진행 속성 값을 설정 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-115">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="2c605-116">진행 속성 값을 가져오는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-116">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="2c605-117">진행 속성과 연결 된 다른 메서드의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-117">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="2c605-118">을 사용 하 여 배열을 종료 `mdTokenNil` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-118">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="2c605-119">제한이 `mdProperty` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-119">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c605-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c605-120">Requirements</span></span>  

 <span data-ttu-id="2c605-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c605-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c605-122">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="2c605-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c605-123">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-123">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c605-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c605-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c605-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c605-125">See also</span></span>

- [<span data-ttu-id="2c605-126">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c605-126">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2c605-127">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c605-127">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

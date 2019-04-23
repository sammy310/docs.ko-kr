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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a67e8ce19a2acf5b4ee1d114858e00d93cb183b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115585"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="5c7c4-102">IMetaDataEmit::DefineMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="5c7c4-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="5c7c4-103">지정된 된 시그니처를 사용 하 여 메서드 또는 전역 함수에 대 한 정의 만들고 해당 메서드 정의에 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c7c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c7c4-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="5c7c4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c7c4-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="5c7c4-106">[in] `mdTypedef` 부모 클래스의 부모 인터페이스 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="5c7c4-107">설정할 `td` 에 `mdTokenNil`전역 함수를 정의 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="5c7c4-108">[in] 유니코드의 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="5c7c4-109">[in] 값을 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 메서드 또는 전역 함수의 특성을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="5c7c4-110">[in] 메서드 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-110">[in] The method signature.</span></span> <span data-ttu-id="5c7c4-111">서명은 제공 하는 대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="5c7c4-112">모든 매개 변수에 대 한 추가 정보를 지정 해야 할 경우 사용 합니다 [imetadataemit:: Setparamprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="5c7c4-113">[in] 바이트 수가 `pvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="5c7c4-114">[in] 코드의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="5c7c4-115">[in] 값을 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 메서드 구현 기능을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="5c7c4-116">[out] 멤버 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c7c4-117">설명</span><span class="sxs-lookup"><span data-stu-id="5c7c4-117">Remarks</span></span>  
 <span data-ttu-id="5c7c4-118">메타 데이터 API 호출자가 내보낸 지정 된 바깥쪽 클래스 또는 인터페이스에 설명 된 대로 동일한 순서로 메서드를 유지 하도록 보장 합니다 `td` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="5c7c4-119">사용과 관련 된 추가 정보 `DefineMethod` 및 특정 매개 변수 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="5c7c4-120">V-테이블의 슬롯</span><span class="sxs-lookup"><span data-stu-id="5c7c4-120">Slots in the V-table</span></span>  
 <span data-ttu-id="5c7c4-121">런타임은은 메서드 정의 사용 하 여 v 테이블 슬롯 설정.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="5c7c4-122">하나 이상의 슬롯 건너뛴, 이러한 해야 하는 경우에는 COM 인터페이스 레이아웃으로 패리티를 유지 하는 것에 대 한 더미 메서드를 정의 슬롯 또는 v-테이블에 대 한 슬롯을 차지 하도록 설정를 `dwMethodFlags` 에 `mdRTSpecialName` 의 값을 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형으로 이름을 지정:</span><span class="sxs-lookup"><span data-stu-id="5c7c4-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="5c7c4-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="5c7c4-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="5c7c4-124">여기서 *SequenceNumber* 메서드의 시퀀스 번호 및 *CountOfSlots* v-table에서 건너뛸 슬롯입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="5c7c4-125">하는 경우 *CountOfSlots* 는 생략 하면 1 이라고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="5c7c4-126">이러한 더미 메서드 또는 비관리 코드에서 호출할 수 없는 및 예외를 생성 하는 관리 코드 또는 비관리 코드에서 호출 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="5c7c4-127">유일한 용도 런타임에서 COM 통합에 대 한 생성 하는 v-테이블의 공간을 차지 하도록입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="5c7c4-128">중복 메서드</span><span class="sxs-lookup"><span data-stu-id="5c7c4-128">Duplicate Methods</span></span>  
 <span data-ttu-id="5c7c4-129">중복 된 메서드를 정의 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-129">You should not define duplicate methods.</span></span> <span data-ttu-id="5c7c4-130">즉, 호출 하면 안 `DefineMethod` 에서 값 중복 집합을 사용 하 여는 `td`, `wzName`, 및 `pvSig` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="5c7c4-131">(이러한 세 개의 매개 변수를 함께 고유 메서드를 정의 합니다.).</span><span class="sxs-lookup"><span data-stu-id="5c7c4-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="5c7c4-132">메서드 정의 중 하나에 대해 설정 된 중복 3을 사용할 수 있지만 합니다 `mdPrivateScope` 비트는 `dwMethodFlags` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="5c7c4-133">(의 `mdPrivateScope` 비트 의미 컴파일러가 메서드 정의에 대 한 참조를 내보내지 것입니다.)</span><span class="sxs-lookup"><span data-stu-id="5c7c4-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="5c7c4-134">메서드 구현 정보</span><span class="sxs-lookup"><span data-stu-id="5c7c4-134">Method Implementation Information</span></span>  
 <span data-ttu-id="5c7c4-135">메서드 구현에 대 한 정보는 메서드가 선언 시 알 수 없습니다 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="5c7c4-136">값을 전달할 필요가 없습니다 따라서 합니다 `ulCodeRVA` 및 `dwImplFlags` 매개 변수를 호출할 때 `DefineMethod`합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="5c7c4-137">값을 통해 나중에 제공할 수 있습니다 [imetadataemit:: Setmethodimplflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) 하거나 [imetadataemit:: Setrva](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)를 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="5c7c4-138">플랫폼 호출 (PInvoke) 또는 COM interop 시나리오에서와 같이 일부 상황에서 메서드 본문은 제공 되지 않으면 및 `ulCodeRVA` 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="5c7c4-139">이러한 상황에서는 메서드 없습니다 태그를 지정 해야 abstract로 런타임 구현의 찾이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="5c7c4-140">PInvoke에 대 한 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="5c7c4-141">PInvoke를 통해 호출할 각 관리 되지 않는 함수에 대 한 관리 되지 않는 대상 함수를 나타내는 관리 되는 메서드를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="5c7c4-142">관리 되는 메서드를 정의 하려면 사용 하 여 `DefineMethod` PInvoke 사용 되는 방식에 따라 특정 값으로 설정 된 매개 변수 중 일부를 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="5c7c4-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
-   <span data-ttu-id="5c7c4-143">PInvoke-관리 되지 않는 DLL에 상주 하는 외부 관리 되지 않는 메서드 호출이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
-   <span data-ttu-id="5c7c4-144">로컬 PInvoke-에 현재 관리 되는 모듈에 포함 된 네이티브 관리 되지 않는 메서드 호출이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="5c7c4-145">매개 변수 설정은 다음 표에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="5c7c4-146">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c7c4-146">Parameter</span></span>|<span data-ttu-id="5c7c4-147">True PInvoke 값</span><span class="sxs-lookup"><span data-stu-id="5c7c4-147">Values for true PInvoke</span></span>|<span data-ttu-id="5c7c4-148">로컬 PInvoke 값</span><span class="sxs-lookup"><span data-stu-id="5c7c4-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="5c7c4-149">설정할 `mdStatic`; 지우기 `mdSynchronized` 및 `mdAbstract`합니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="5c7c4-150">유효한 공용 언어 런타임 (CLR) 메서드 서명이 잘못 된 매개 변수를 사용 하 여 관리 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="5c7c4-151">유효한 CLR 메서드 서명이 잘못 된 매개 변수를 사용 하 여 관리 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="5c7c4-152">0</span><span class="sxs-lookup"><span data-stu-id="5c7c4-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="5c7c4-153">설정할 `miCil` 고 `miManaged`입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="5c7c4-154">설정할 `miNative` 고 `miUnmanaged`입니다.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c7c4-155">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c7c4-155">Requirements</span></span>  
 <span data-ttu-id="5c7c4-156">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c7c4-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c7c4-157">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5c7c4-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c7c4-158">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5c7c4-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c7c4-159">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c7c4-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c7c4-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c7c4-160">See also</span></span>

- [<span data-ttu-id="5c7c4-161">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c7c4-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5c7c4-162">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c7c4-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

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
ms.openlocfilehash: a32a1eb850943b84a0d368f883e44fd4ccf32ee9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719582"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="cc632-102">IMetaDataEmit::DefineMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="cc632-102">IMetaDataEmit::DefineMethod Method</span></span>

<span data-ttu-id="cc632-103">지정 된 서명을 사용 하 여 메서드 또는 전역 함수에 대 한 정의를 만들고 해당 메서드 정의에 대 한 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc632-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc632-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="cc632-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc632-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="cc632-106">진행 `mdTypedef` 메서드의 부모 클래스 또는 부모 인터페이스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="cc632-107">`td` `mdTokenNil` 전역 함수를 정의 하는 경우로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="cc632-108">진행 유니코드로 된 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="cc632-109">진행 메서드 또는 전역 함수의 특성을 지정 하는 [CorMethodAttr](cormethodattr-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-109">[in] A value of the [CorMethodAttr](cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="cc632-110">진행 메서드 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-110">[in] The method signature.</span></span> <span data-ttu-id="cc632-111">제공 된 대로 서명이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="cc632-112">매개 변수에 대 한 추가 정보를 지정 해야 하는 경우 [IMetaDataEmit:: SetParamProps](imetadataemit-setparamprops-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="cc632-113">진행 의 바이트 수 `pvSigBlob` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="cc632-114">진행 코드의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="cc632-115">진행 메서드의 구현 기능을 지정 하는 [Cormethodimpl](cormethodimpl-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-115">[in] A value of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="cc632-116">제한이 멤버 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc632-117">설명</span><span class="sxs-lookup"><span data-stu-id="cc632-117">Remarks</span></span>  

 <span data-ttu-id="cc632-118">메타 데이터 API는 호출자가 매개 변수에 지정 된 지정 된 바깥쪽 클래스 또는 인터페이스에 대해 메서드를 내보내는 것과 동일한 순서로 메서드를 유지 하도록 보장 합니다 `td` .</span><span class="sxs-lookup"><span data-stu-id="cc632-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="cc632-119">`DefineMethod`및 특정 매개 변수 설정 사용에 대 한 추가 정보는 아래에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="cc632-120">V 테이블의 슬롯</span><span class="sxs-lookup"><span data-stu-id="cc632-120">Slots in the V-table</span></span>  

 <span data-ttu-id="cc632-121">런타임은 메서드 정의를 사용 하 여 v 테이블 슬롯을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="cc632-122">COM 인터페이스 레이아웃을 사용 하 여 패리티를 유지 하는 등 하나 이상의 슬롯을 건너뛰어야 하는 경우 더미 메서드는 v-table의 슬롯을 차지 하도록 정의 됩니다. 을 `dwMethodFlags` `mdRTSpecialName` [CorMethodAttr](cormethodattr-enumeration.md) 열거형의 값으로 설정 하 고 이름을 다음과 같이 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="cc632-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="cc632-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="cc632-124">여기서 *SequenceNumber* 는 메서드의 시퀀스 번호이 고 *CountOfSlots* 는 v 테이블에서 건너뛸 슬롯 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="cc632-125">*CountOfSlots* 를 생략 하면 1이 가정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="cc632-126">이러한 더미 메서드는 관리 코드 또는 비관리 코드에서 호출할 수 없으며 관리 코드 또는 비관리 코드에서 호출 하려고 하면 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="cc632-127">유일한 용도는 런타임에서 COM 통합을 위해 생성 하는 v-table의 공간을 차지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="cc632-128">중복 메서드</span><span class="sxs-lookup"><span data-stu-id="cc632-128">Duplicate Methods</span></span>  

 <span data-ttu-id="cc632-129">중복 메서드를 정의 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-129">You should not define duplicate methods.</span></span> <span data-ttu-id="cc632-130">즉,, `DefineMethod` `td` `wzName` 및 매개 변수에서 중복 값 집합을 사용 하 여를 호출 하면 안 됩니다 `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="cc632-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="cc632-131">이 세 매개 변수는 메서드를 고유 하 게 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="cc632-132">그러나 메서드 정의 중 하나에 대해 `mdPrivateScope` 매개 변수에서 비트를 설정 하는 경우 중복 된 삼중을 사용할 수 있습니다 `dwMethodFlags` .</span><span class="sxs-lookup"><span data-stu-id="cc632-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="cc632-133">비트는 `mdPrivateScope` 컴파일러에서이 메서드 정의에 대 한 참조를 내보내지 않는다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="cc632-134">메서드 구현 정보</span><span class="sxs-lookup"><span data-stu-id="cc632-134">Method Implementation Information</span></span>  

 <span data-ttu-id="cc632-135">메서드 구현에 대 한 정보는 메서드가 선언 될 때 알려지지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="cc632-136">따라서를 `ulCodeRVA` `dwImplFlags` 호출할 때 및 매개 변수에 값을 전달할 필요가 없습니다 `DefineMethod` .</span><span class="sxs-lookup"><span data-stu-id="cc632-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="cc632-137">이러한 값은 나중에 [IMetaDataEmit:: SetMethodImplFlags](imetadataemit-setmethodimplflags-method.md) 또는 [IMetaDataEmit:: setrva](imetadataemit-setrva-method.md)를 통해 적절 하 게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="cc632-138">플랫폼 호출 (PInvoke) 또는 COM interop 시나리오와 같은 경우에는 메서드 본문이 제공 되지 않으므로 `ulCodeRVA` 0으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="cc632-139">이러한 경우 런타임이 구현을 찾기 때문에 메서드는 abstract로 태그를 지정 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="cc632-140">PInvoke에 대 한 메서드 정의</span><span class="sxs-lookup"><span data-stu-id="cc632-140">Defining a Method for PInvoke</span></span>  

 <span data-ttu-id="cc632-141">PInvoke를 통해 호출 되는 관리 되지 않는 각 함수에 대해 대상 관리 되지 않는 함수를 나타내는 관리 되는 메서드를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="cc632-142">관리 되는 메서드를 정의 하려면 `DefineMethod` PInvoke를 사용 하는 방식에 따라 특정 값으로 설정 된 몇 가지 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="cc632-143">True PInvoke-관리 되지 않는 DLL에 상주 하는 관리 되지 않는 외부 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="cc632-144">로컬 PInvoke-현재 관리 되는 모듈에 포함 된 관리 되지 않는 네이티브 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="cc632-145">다음 표에서는 매개 변수 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="cc632-146">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc632-146">Parameter</span></span>|<span data-ttu-id="cc632-147">True PInvoke 값</span><span class="sxs-lookup"><span data-stu-id="cc632-147">Values for true PInvoke</span></span>|<span data-ttu-id="cc632-148">로컬 PInvoke 값</span><span class="sxs-lookup"><span data-stu-id="cc632-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="cc632-149">Set `mdStatic` , `mdSynchronized` 및을 선택 취소 `mdAbstract` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="cc632-150">유효한 관리 되는 형식인 매개 변수가 포함 된 유효한 CLR (공용 언어 런타임) 메서드 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="cc632-151">유효한 관리 되는 형식인 매개 변수가 포함 된 유효한 CLR 메서드 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="cc632-152">0</span><span class="sxs-lookup"><span data-stu-id="cc632-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="cc632-153">`miCil` 및 `miManaged`를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="cc632-154">`miNative` 및 `miUnmanaged`를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc632-155">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc632-155">Requirements</span></span>  

 <span data-ttu-id="cc632-156">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc632-156">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc632-157">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="cc632-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc632-158">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc632-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc632-159">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc632-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc632-160">참조</span><span class="sxs-lookup"><span data-stu-id="cc632-160">See also</span></span>

- [<span data-ttu-id="cc632-161">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc632-161">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="cc632-162">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc632-162">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

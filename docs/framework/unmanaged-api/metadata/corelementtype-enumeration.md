---
description: '자세한 정보: CorElementType 열거형'
title: CorElementType 열거형
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
ms.openlocfilehash: 3eaf75a6d2094ec875ab1861aac49e4382e65801
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784537"
---
# <a name="corelementtype-enumeration"></a><span data-ttu-id="a7566-103">CorElementType 열거형</span><span class="sxs-lookup"><span data-stu-id="a7566-103">CorElementType Enumeration</span></span>

<span data-ttu-id="a7566-104"><xref:System.Type>메타 데이터 형식 시그니처의 형식에 대 한 공용 언어 런타임, 형식 한정자 또는 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-104">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7566-105">구문</span><span class="sxs-lookup"><span data-stu-id="a7566-105">Syntax</span></span>

```cpp
typedef enum CorElementType {
    ELEMENT_TYPE_END            = 0x0,
    ELEMENT_TYPE_VOID           = 0x1,
    ELEMENT_TYPE_BOOLEAN        = 0x2,
    ELEMENT_TYPE_CHAR           = 0x3,
    ELEMENT_TYPE_I1             = 0x4,
    ELEMENT_TYPE_U1             = 0x5,
    ELEMENT_TYPE_I2             = 0x6,
    ELEMENT_TYPE_U2             = 0x7,
    ELEMENT_TYPE_I4             = 0x8,
    ELEMENT_TYPE_U4             = 0x9,
    ELEMENT_TYPE_I8             = 0xa,
    ELEMENT_TYPE_U8             = 0xb,
    ELEMENT_TYPE_R4             = 0xc,
    ELEMENT_TYPE_R8             = 0xd,
    ELEMENT_TYPE_STRING         = 0xe,

    ELEMENT_TYPE_PTR            = 0xf,
    ELEMENT_TYPE_BYREF          = 0x10,

    ELEMENT_TYPE_VALUETYPE      = 0x11,
    ELEMENT_TYPE_CLASS          = 0x12,
    ELEMENT_TYPE_VAR            = 0x13,
    ELEMENT_TYPE_ARRAY          = 0x14,
    ELEMENT_TYPE_GENERICINST    = 0x15,
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,

    ELEMENT_TYPE_I              = 0x18,
    ELEMENT_TYPE_U              = 0x19,
    ELEMENT_TYPE_FNPTR          = 0x1B,
    ELEMENT_TYPE_OBJECT         = 0x1C,
    ELEMENT_TYPE_SZARRAY        = 0x1D,
    ELEMENT_TYPE_MVAR           = 0x1e,

    ELEMENT_TYPE_CMOD_REQD      = 0x1F,
    ELEMENT_TYPE_CMOD_OPT       = 0x20,

    ELEMENT_TYPE_INTERNAL       = 0x21,
    ELEMENT_TYPE_MAX            = 0x22,

    ELEMENT_TYPE_MODIFIER       = 0x40,
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER

} CorElementType;
```

## <a name="members"></a><span data-ttu-id="a7566-106">구성원</span><span class="sxs-lookup"><span data-stu-id="a7566-106">Members</span></span>

|<span data-ttu-id="a7566-107">멤버</span><span class="sxs-lookup"><span data-stu-id="a7566-107">Member</span></span>|<span data-ttu-id="a7566-108">설명</span><span class="sxs-lookup"><span data-stu-id="a7566-108">Description</span></span>|
|------------|-----------------|
|`ELEMENT_TYPE_END`|<span data-ttu-id="a7566-109">내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-109">Used internally.</span></span>|
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="a7566-110">Void 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-110">A void type.</span></span>|
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="a7566-111">부울 형식</span><span class="sxs-lookup"><span data-stu-id="a7566-111">A Boolean type</span></span>|
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="a7566-112">문자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-112">A character type.</span></span>|
|`ELEMENT_TYPE_I1`|<span data-ttu-id="a7566-113">부호 있는 1 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-113">A signed 1-byte integer.</span></span>|
|`ELEMENT_TYPE_U1`|<span data-ttu-id="a7566-114">부호 없는 1바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-114">An unsigned 1-byte integer.</span></span>|
|`ELEMENT_TYPE_I2`|<span data-ttu-id="a7566-115">부호 있는 2 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-115">A signed 2-byte integer.</span></span>|
|`ELEMENT_TYPE_U2`|<span data-ttu-id="a7566-116">부호 없는 2 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-116">An unsigned 2-byte integer.</span></span>|
|`ELEMENT_TYPE_I4`|<span data-ttu-id="a7566-117">부호 있는 4 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-117">A signed 4-byte integer.</span></span>|
|`ELEMENT_TYPE_U4`|<span data-ttu-id="a7566-118">부호 없는 4 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-118">An unsigned 4-byte integer.</span></span>|
|`ELEMENT_TYPE_I8`|<span data-ttu-id="a7566-119">부호 있는 8 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-119">A signed 8-byte integer.</span></span>|
|`ELEMENT_TYPE_U8`|<span data-ttu-id="a7566-120">부호 없는 8 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-120">An unsigned 8-byte integer.</span></span>|
|`ELEMENT_TYPE_R4`|<span data-ttu-id="a7566-121">4 바이트 부동 소수점입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-121">A 4-byte floating point.</span></span>|
|`ELEMENT_TYPE_R8`|<span data-ttu-id="a7566-122">8 바이트 부동 소수점입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-122">An 8-byte floating point.</span></span>|
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="a7566-123">System.string 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-123">A System.String type.</span></span>|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="a7566-124">포인터 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-124">A pointer type modifier.</span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="a7566-125">참조 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-125">A reference type modifier.</span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="a7566-126">값 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-126">A value type modifier.</span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="a7566-127">클래스 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-127">A class type modifier.</span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="a7566-128">클래스 변수 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-128">A class variable type modifier.</span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="a7566-129">다차원 배열 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-129">A multi-dimensional array type modifier.</span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="a7566-130">제네릭 형식에 대 한 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-130">A type modifier for generic types.</span></span>|
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="a7566-131">형식화된 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-131">A typed reference.</span></span>|
|`ELEMENT_TYPE_I`|<span data-ttu-id="a7566-132">네이티브 정수의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-132">Size of a native integer.</span></span>|
|`ELEMENT_TYPE_U`|<span data-ttu-id="a7566-133">부호 없는 네이티브 정수의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-133">Size of an unsigned native integer.</span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="a7566-134">함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-134">A pointer to a function.</span></span>|
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="a7566-135">System.object 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-135">A System.Object type.</span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="a7566-136">0이 아닌 1 차원 배열 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-136">A single-dimensional, zero lower-bound array type modifier.</span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="a7566-137">메서드 변수 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-137">A method variable type modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="a7566-138">C 언어 필수 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-138">A C language required modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="a7566-139">C 언어 선택적 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-139">A C language optional modifier.</span></span>|
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="a7566-140">내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-140">Used internally.</span></span>|
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="a7566-141">잘못된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-141">An invalid type.</span></span>|
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="a7566-142">내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-142">Used internally.</span></span>|
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="a7566-143">변수 수의 변수 목록에 대 한 센티널 인 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-143">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="a7566-144">내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-144">Used internally.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a7566-145">설명</span><span class="sxs-lookup"><span data-stu-id="a7566-145">Remarks</span></span>

<span data-ttu-id="a7566-146">형식 한정자는 보다 복잡 한 형식을 나타내는 기본을 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-146">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="a7566-147">형식 `CorElementType` 한정자 값은 형식 시그니처에서 바로 다음에 오는 값에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-147">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="a7566-148">`CorElementType`다음 표에 지정 된 것 처럼 형식 한정자 값 다음에 오는 값은 `CorElementType` 단순 형식 값, 메타 데이터 토큰 또는 다른 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-148">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="a7566-149">모든 숫자 (*숫자*, *인수 개수*, *메타 데이터 토큰*, *순위*, *개수* 및 *바운드*)는 압축 된 정수로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7566-149">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="a7566-150">자세한 내용은 ECMA 웹 사이트의 [표준 ECMA-335-CLI (공용 언어 인프라)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a7566-150">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) on the ECMA Web site for details.</span></span>

|<span data-ttu-id="a7566-151">형식 한정자</span><span class="sxs-lookup"><span data-stu-id="a7566-151">Type modifier</span></span>|<span data-ttu-id="a7566-152">서식</span><span class="sxs-lookup"><span data-stu-id="a7566-152">Format</span></span>|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="a7566-153">ELEMENT_TYPE_PTR \<a `CorElementType` value></span><span class="sxs-lookup"><span data-stu-id="a7566-153">ELEMENT_TYPE_PTR \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="a7566-154">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span><span class="sxs-lookup"><span data-stu-id="a7566-154">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="a7566-155">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span><span class="sxs-lookup"><span data-stu-id="a7566-155">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="a7566-156">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span><span class="sxs-lookup"><span data-stu-id="a7566-156">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="a7566-157">ELEMENT_TYPE_VAR \<number></span><span class="sxs-lookup"><span data-stu-id="a7566-157">ELEMENT_TYPE_VAR \<number></span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="a7566-158">\<a `CorElementType` value> \<rank> \<count1> \<bound1> ELEMENT_TYPE_ARRAY ... \<countN>\<boundN></span><span class="sxs-lookup"><span data-stu-id="a7566-158">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="a7566-159">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> ... \<argument Count> \<arg1>\<argN></span><span class="sxs-lookup"><span data-stu-id="a7566-159">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="a7566-160">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span><span class="sxs-lookup"><span data-stu-id="a7566-160">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="a7566-161">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span><span class="sxs-lookup"><span data-stu-id="a7566-161">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="a7566-162">ELEMENT_TYPE_MVAR \<number></span><span class="sxs-lookup"><span data-stu-id="a7566-162">ELEMENT_TYPE_MVAR \<number></span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="a7566-163">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span><span class="sxs-lookup"><span data-stu-id="a7566-163">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="a7566-164">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span><span class="sxs-lookup"><span data-stu-id="a7566-164">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|

## <a name="requirements"></a><span data-ttu-id="a7566-165">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7566-165">Requirements</span></span>

<span data-ttu-id="a7566-166">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7566-166">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="a7566-167">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="a7566-167">**Header:** CorHdr.h</span></span>

<span data-ttu-id="a7566-168">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7566-168">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a7566-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7566-169">See also</span></span>

- [<span data-ttu-id="a7566-170">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="a7566-170">Metadata Enumerations</span></span>](metadata-enumerations.md)

---
title: CorElementType 열거형1
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d47e250a35640d15bd494d99442271a070a1dd0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781909"
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="aa8b9-102">CorElementType 열거형1</span><span class="sxs-lookup"><span data-stu-id="aa8b9-102">CorElementType Enumeration1</span></span>

<span data-ttu-id="aa8b9-103">공용 언어 런타임을 지정 <xref:System.Type>, 형식 한정자 또는 메타 데이터 형식 서명에서 형식에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa8b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa8b9-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="aa8b9-105">멤버</span><span class="sxs-lookup"><span data-stu-id="aa8b9-105">Members</span></span>

|<span data-ttu-id="aa8b9-106">멤버</span><span class="sxs-lookup"><span data-stu-id="aa8b9-106">Member</span></span>|<span data-ttu-id="aa8b9-107">설명</span><span class="sxs-lookup"><span data-stu-id="aa8b9-107">Description</span></span>|
|------------|-----------------|
|`ELEMENT_TYPE_END`|<span data-ttu-id="aa8b9-108">내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-108">Used internally.</span></span>|
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="aa8b9-109">Void 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-109">A void type.</span></span>|
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="aa8b9-110">부울 형식</span><span class="sxs-lookup"><span data-stu-id="aa8b9-110">A Boolean type</span></span>|
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="aa8b9-111">문자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-111">A character type.</span></span>|
|`ELEMENT_TYPE_I1`|<span data-ttu-id="aa8b9-112">부호 있는 1 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-112">A signed 1-byte integer.</span></span>|
|`ELEMENT_TYPE_U1`|<span data-ttu-id="aa8b9-113">부호 없는 1바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-113">An unsigned 1-byte integer.</span></span>|
|`ELEMENT_TYPE_I2`|<span data-ttu-id="aa8b9-114">부호 있는 2 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-114">A signed 2-byte integer.</span></span>|
|`ELEMENT_TYPE_U2`|<span data-ttu-id="aa8b9-115">부호 없는 2 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-115">An unsigned 2-byte integer.</span></span>|
|`ELEMENT_TYPE_I4`|<span data-ttu-id="aa8b9-116">부호 있는 4 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-116">A signed 4-byte integer.</span></span>|
|`ELEMENT_TYPE_U4`|<span data-ttu-id="aa8b9-117">부호 없는 4 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-117">An unsigned 4-byte integer.</span></span>|
|`ELEMENT_TYPE_I8`|<span data-ttu-id="aa8b9-118">부호 있는 8 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-118">A signed 8-byte integer.</span></span>|
|`ELEMENT_TYPE_U8`|<span data-ttu-id="aa8b9-119">부호 없는 8 바이트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-119">An unsigned 8-byte integer.</span></span>|
|`ELEMENT_TYPE_R4`|<span data-ttu-id="aa8b9-120">4 바이트 부동 소수점입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-120">A 4-byte floating point.</span></span>|
|`ELEMENT_TYPE_R8`|<span data-ttu-id="aa8b9-121">8 바이트 부동 소수점입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-121">An 8-byte floating point.</span></span>|
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="aa8b9-122">System.String 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-122">A System.String type.</span></span>|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="aa8b9-123">포인터 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-123">A pointer type modifier.</span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="aa8b9-124">참조 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-124">A reference type modifier.</span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="aa8b9-125">값 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-125">A value type modifier.</span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="aa8b9-126">클래스 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-126">A class type modifier.</span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="aa8b9-127">클래스 변수 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-127">A class variable type modifier.</span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="aa8b9-128">다차원 배열 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-128">A multi-dimensional array type modifier.</span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="aa8b9-129">제네릭 형식에 대 한 유형 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-129">A type modifier for generic types.</span></span>|
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="aa8b9-130">형식화된 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-130">A typed reference.</span></span>|
|`ELEMENT_TYPE_I`|<span data-ttu-id="aa8b9-131">네이티브 정수 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-131">Size of a native integer.</span></span>|
|`ELEMENT_TYPE_U`|<span data-ttu-id="aa8b9-132">부호 없는 기본 정수 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-132">Size of an unsigned native integer.</span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="aa8b9-133">함수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-133">A pointer to a function.</span></span>|
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="aa8b9-134">System.Object 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-134">A System.Object type.</span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="aa8b9-135">단일 차원, 0 인 배열 형식 한정자</span><span class="sxs-lookup"><span data-stu-id="aa8b9-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="aa8b9-136">메서드 변수 형식 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-136">A method variable type modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="aa8b9-137">C 언어는 필수 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-137">A C language required modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="aa8b9-138">C 언어의 선택적 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-138">A C language optional modifier.</span></span>|
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="aa8b9-139">내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-139">Used internally.</span></span>|
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="aa8b9-140">잘못된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-140">An invalid type.</span></span>|
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="aa8b9-141">내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-141">Used internally.</span></span>|
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="aa8b9-142">형식 한정자는 가변 개수의 매개 변수 목록은 sentinel입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="aa8b9-143">내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-143">Used internally.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa8b9-144">설명</span><span class="sxs-lookup"><span data-stu-id="aa8b9-144">Remarks</span></span>

<span data-ttu-id="aa8b9-145">형식 한정자는 더 복잡 한 형식을 나타내는 기반을 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="aa8b9-146">`CorElementType` 형식 한정자 값이 바로 뒤에 오는 형식 서명의 값에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="aa8b9-147">뒤에 오는 값을 `CorElementType` 형식 한정자 값 수를 `CorElementType` 단순 유형 값, 메타 데이터 토큰, 또는 다른 값을 다음 표에 지정 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="aa8b9-148">모든 숫자 (*수*, *인수 개수*를 *메타 데이터 토큰*를 *순위*를 *개수*, 및 *바인딩된*) 압축 된 정수로 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="aa8b9-149">참조 [표준 ECMA-335-CLI 공용 언어 인프라 ()](https://go.microsoft.com/fwlink/?LinkID=116487) 대 한 자세한 내용은 ECMA 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>

|<span data-ttu-id="aa8b9-150">형식 한정자</span><span class="sxs-lookup"><span data-stu-id="aa8b9-150">Type modifier</span></span>|<span data-ttu-id="aa8b9-151">형식</span><span class="sxs-lookup"><span data-stu-id="aa8b9-151">Format</span></span>|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="aa8b9-152">ELEMENT_TYPE_PTR \<는 `CorElementType` 값 ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-152">ELEMENT_TYPE_PTR \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="aa8b9-153">ELEMENT_TYPE_BYREF \<는 `CorElementType` 값 ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-153">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="aa8b9-154">ELEMENT_TYPE_VALUETYPE \<는 `mdTypeDef` 메타 데이터 토큰 ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-154">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="aa8b9-155">ELEMENT_TYPE_CLASS \<는 `mdTypeDef` 메타 데이터 토큰 ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-155">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="aa8b9-156">ELEMENT_TYPE_VAR \<번호 ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-156">ELEMENT_TYPE_VAR \<number></span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="aa8b9-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span><span class="sxs-lookup"><span data-stu-id="aa8b9-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="aa8b9-158">ELEMENT_TYPE_GENERICINST \<는 `mdTypeDef` 메타 데이터 토큰 > \<인수 개수 > \<arg1 >... \<argN ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-158">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="aa8b9-159">Typ ELEMENT_TYPE_FNPTR \<호출 규칙이 포함 된 함수에 대 한 전체 시그니처 ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="aa8b9-160">ELEMENT_TYPE_SZARRAY \<는 `CorElementType` 값 ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-160">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="aa8b9-161">ELEMENT_TYPE_MVAR \<number></span><span class="sxs-lookup"><span data-stu-id="aa8b9-161">ELEMENT_TYPE_MVAR \<number></span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="aa8b9-162">ELEMENT_TYPE_\<는 `mdTypeRef` 또는 `mdTypeDef` 메타 데이터 토큰 ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-162">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="aa8b9-163">E_T_CMOD_OPT \<는 `mdTypeRef` 또는 `mdTypeDef` 메타 데이터 토큰 ></span><span class="sxs-lookup"><span data-stu-id="aa8b9-163">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|

## <a name="requirements"></a><span data-ttu-id="aa8b9-164">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa8b9-164">Requirements</span></span>

<span data-ttu-id="aa8b9-165">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa8b9-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="aa8b9-166">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="aa8b9-166">**Header:** CorHdr.h</span></span>

<span data-ttu-id="aa8b9-167">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa8b9-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="aa8b9-168">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa8b9-168">See also</span></span>

- [<span data-ttu-id="aa8b9-169">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="aa8b9-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)

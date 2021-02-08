---
description: '자세히 알아보기: CorNativeType 열거형'
title: CorNativeType 열거형
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
ms.openlocfilehash: d2313eef124f3308c4792b47da8b7c8bba984597
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784329"
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="aa59f-103">CorNativeType 열거형</span><span class="sxs-lookup"><span data-stu-id="aa59f-103">CorNativeType Enumeration</span></span>

<span data-ttu-id="aa59f-104">관리되지 않는 네이티브 형식을 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-104">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa59f-105">구문</span><span class="sxs-lookup"><span data-stu-id="aa59f-105">Syntax</span></span>  
  
```cpp  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a><span data-ttu-id="aa59f-106">구성원</span><span class="sxs-lookup"><span data-stu-id="aa59f-106">Members</span></span>  
  
|<span data-ttu-id="aa59f-107">멤버</span><span class="sxs-lookup"><span data-stu-id="aa59f-107">Member</span></span>|<span data-ttu-id="aa59f-108">설명</span><span class="sxs-lookup"><span data-stu-id="aa59f-108">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="aa59f-109">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="aa59f-110">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-110">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="aa59f-111">4 바이트 부울 값입니다. 여기서 TRUE는 0이 아니고 FALSE는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-111">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="aa59f-112">부호 있는 8 비트 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-112">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="aa59f-113">부호 없는 8 비트 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-113">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="aa59f-114">부호 있는 16 비트 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-114">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="aa59f-115">부호 없는 16 비트 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-115">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="aa59f-116">부호 있는 32비트 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-116">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="aa59f-117">부호 없는 32비트 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-117">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="aa59f-118">부호 있는 64 비트 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-118">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="aa59f-119">부호 없는 64 비트 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-119">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="aa59f-120">4 바이트 부동 소수점 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-120">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="aa59f-121">8 바이트 부동 소수점 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-121">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="aa59f-122">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="aa59f-123">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-123">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="aa59f-124">관리 되는 형식에 해당 하는 숫자 COM 형식 <xref:System.Decimal> 입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-124">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="aa59f-125">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="aa59f-126">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="aa59f-127">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-127">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="aa59f-128">COM Interop를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-128">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="aa59f-129">LPSTR 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-129">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="aa59f-130">LPWSTR 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-130">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="aa59f-131">LPTSTR 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-131">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="aa59f-132">수정 된 시스템 정의 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-132">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="aa59f-133">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-133">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="aa59f-134">COM Interop를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="aa59f-135">COM Interop를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-135">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="aa59f-136">네이티브 구조체 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-136">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="aa59f-137">COM Interop를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="aa59f-138">COM Interop를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-138">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="aa59f-139">고정 길이 배열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-139">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="aa59f-140">네이티브 16 비트 부호 있는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-140">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="aa59f-141">네이티브 16 비트 부호 없는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-141">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="aa59f-142">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-142">Obsolete.</span></span><br /><br /> <span data-ttu-id="aa59f-143">NATIVE_TYPE_STRUCT를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-143">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="aa59f-144">COM Interop를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="aa59f-145">COM Interop를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-145">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="aa59f-146">COM Interop를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-146">COM Interop.</span></span><br /><br /> <span data-ttu-id="aa59f-147">플랫폼에 따라 BSTR 또는 ANSIBSTR를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-147">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="aa59f-148">2 바이트 부울 값입니다. 여기서 TRUE는-1이 고 FALSE는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-148">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="aa59f-149">함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-149">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="aa59f-150">네이티브 형식에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-150">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="aa59f-151">지정 되지 않은 형식의 멤버가 있는 배열에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-151">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="aa59f-152">구조체에 대 한 32 비트 정수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-152">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="aa59f-153">사용자 지정 마샬러 네이티브 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-153">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="aa59f-154">다음 형식의 문자열이 뒤에와 야 합니다. "네이티브 형식 이름/0 사용자 지정 마샬러 형식 이름/0 선택적 쿠키/0" 또는 "{네이티브 형식 GUID} (사용자 지정 마샬러 형식 이름/0 선택적 쿠키/0")</span><span class="sxs-lookup"><span data-stu-id="aa59f-154">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="aa59f-155">COM Interop를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-155">COM Interop.</span></span><br /><br /> <span data-ttu-id="aa59f-156">ELEMENT_TYPE_I4이 형식은 VT_HRESULT에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-156">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="aa59f-157">네이티브 `IInspectable` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-157">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="aa59f-158">네이티브 `HString` 입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-158">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="aa59f-159">잘못된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="aa59f-159">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa59f-160">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa59f-160">Requirements</span></span>  

 <span data-ttu-id="aa59f-161">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa59f-161">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa59f-162">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="aa59f-162">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="aa59f-163">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa59f-163">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa59f-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa59f-164">See also</span></span>

- <xref:System.Runtime.InteropServices.UnmanagedType>
- [<span data-ttu-id="aa59f-165">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="aa59f-165">Metadata Enumerations</span></span>](metadata-enumerations.md)

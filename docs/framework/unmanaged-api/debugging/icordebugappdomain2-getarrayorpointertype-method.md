---
title: ICorDebugAppDomain2::GetArrayOrPointerType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
ms.openlocfilehash: bbf43f3936823b9a8e562cb32cfa2eef08840033
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895180"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="074b1-102">ICorDebugAppDomain2::GetArrayOrPointerType 메서드</span><span class="sxs-lookup"><span data-stu-id="074b1-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="074b1-103">지정 된 형식의 배열 또는 지정 된 형식에 대 한 포인터 또는 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="074b1-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="074b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="074b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="074b1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="074b1-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="074b1-106">진행 만들 기본 네이티브 형식 (배열, 포인터 또는 참조)을 지정 하는 CorElementType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="074b1-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="074b1-107">진행 배열의 차수 (차원의 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="074b1-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="074b1-108">가 포인터나 참조 형식을 지정 하 `elementType` 는 경우이 값은 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="074b1-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="074b1-109">진행 만들 배열, 포인터 또는 참조의 형식을 나타내는 ICorDebugType 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="074b1-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="074b1-110">제한이 생성 된 배열, 포인터 형식 또는 `ICorDebugType` 참조 형식을 나타내는 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="074b1-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="074b1-111">설명</span><span class="sxs-lookup"><span data-stu-id="074b1-111">Remarks</span></span>  
 <span data-ttu-id="074b1-112">*ElementType* 의 값은 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="074b1-112">The value of *elementType* must be one of the following:</span></span>  
  
- <span data-ttu-id="074b1-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="074b1-113">ELEMENT_TYPE_PTR</span></span>  
  
- <span data-ttu-id="074b1-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="074b1-114">ELEMENT_TYPE_BYREF</span></span>  
  
- <span data-ttu-id="074b1-115">ELEMENT_TYPE_ARRAY 또는 ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="074b1-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="074b1-116">*ElementType* 의 값이 ELEMENT_TYPE_PTR 또는 ELEMENT_TYPE_BYREF 이면 *n rank* 는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="074b1-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="074b1-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="074b1-117">Requirements</span></span>  
 <span data-ttu-id="074b1-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="074b1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="074b1-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="074b1-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="074b1-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="074b1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="074b1-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="074b1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

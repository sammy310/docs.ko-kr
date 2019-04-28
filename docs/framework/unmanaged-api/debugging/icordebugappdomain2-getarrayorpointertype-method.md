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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58a39771bd89fc9c4947f80a3c87b4d340b5461c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934929"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a><span data-ttu-id="9b8ee-102">ICorDebugAppDomain2::GetArrayOrPointerType 메서드</span><span class="sxs-lookup"><span data-stu-id="9b8ee-102">ICorDebugAppDomain2::GetArrayOrPointerType Method</span></span>
<span data-ttu-id="9b8ee-103">지정된 된 형식에 대 한 포인터 또는 지정된 된 형식에 대 한 참조의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9b8ee-103">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b8ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b8ee-104">Syntax</span></span>  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b8ee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b8ee-105">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="9b8ee-106">[in] 기본 네이티브 형식 (배열, 포인터 또는 참조)를 만들 수를 지정 하는 CorElementType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b8ee-106">[in] A value of the CorElementType enumeration that specifies the underlying native type (an array, pointer, or reference) to be created.</span></span>  
  
 `nRank`  
 <span data-ttu-id="9b8ee-107">[in] 배열의 순위 (차원의 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="9b8ee-107">[in] The rank (that is, number of dimensions) of the array.</span></span> <span data-ttu-id="9b8ee-108">이 값은 0 이어야 하는 경우 `elementType` 포인터 또는 참조 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8ee-108">This value must be 0 if `elementType` specifies a pointer or reference type.</span></span>  
  
 `pTypeArg`  
 <span data-ttu-id="9b8ee-109">[in] 배열의 형식을 나타내는 ICorDebugType 개체에 대 한 포인터, 포인터 또는 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b8ee-109">[in] A pointer to an ICorDebugType object that represents the type of array, pointer, or reference to be created.</span></span>  
  
 `ppType`  
 <span data-ttu-id="9b8ee-110">[out] 주소에 대 한 포인터는 `ICorDebugType` 생성 된 배열, 포인터 형식 또는 참조를 나타내는 개체를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8ee-110">[out] A pointer to the address of an `ICorDebugType` object that represents the constructed array, pointer type, or reference type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b8ee-111">설명</span><span class="sxs-lookup"><span data-stu-id="9b8ee-111">Remarks</span></span>  
 <span data-ttu-id="9b8ee-112">변수의 *elementType* 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8ee-112">The value of *elementType* must be one of the following:</span></span>  
  
- <span data-ttu-id="9b8ee-113">ELEMENT_TYPE_PTR</span><span class="sxs-lookup"><span data-stu-id="9b8ee-113">ELEMENT_TYPE_PTR</span></span>  
  
- <span data-ttu-id="9b8ee-114">ELEMENT_TYPE_BYREF</span><span class="sxs-lookup"><span data-stu-id="9b8ee-114">ELEMENT_TYPE_BYREF</span></span>  
  
- <span data-ttu-id="9b8ee-115">ELEMENT_TYPE_ARRAY 또는 ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="9b8ee-115">ELEMENT_TYPE_ARRAY or ELEMENT_TYPE_SZARRAY</span></span>  
  
 <span data-ttu-id="9b8ee-116">경우 값 *elementType* ELEMENT_TYPE_PTR 인지, ELEMENT_TYPE_BYREF *nRank* 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8ee-116">If the value of *elementType* is ELEMENT_TYPE_PTR or ELEMENT_TYPE_BYREF, *nRank* must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b8ee-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b8ee-117">Requirements</span></span>  
 <span data-ttu-id="9b8ee-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b8ee-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b8ee-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b8ee-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b8ee-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b8ee-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b8ee-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b8ee-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

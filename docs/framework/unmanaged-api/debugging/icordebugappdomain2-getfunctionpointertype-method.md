---
description: '자세히 알아보기: ICorDebugAppDomain2:: GetFunctionPointerType 메서드'
title: ICorDebugAppDomain2::GetFunctionPointerType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
ms.openlocfilehash: 2b9e10295df40b8e7db82e489fe8a6d28214ff38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772395"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="bcd0b-103">ICorDebugAppDomain2::GetFunctionPointerType 메서드</span><span class="sxs-lookup"><span data-stu-id="bcd0b-103">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>

<span data-ttu-id="bcd0b-104">지정 된 서명이 있는 함수에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bcd0b-104">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd0b-105">구문</span><span class="sxs-lookup"><span data-stu-id="bcd0b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcd0b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bcd0b-106">Parameters</span></span>  

 `nTypeArgs`  
 <span data-ttu-id="bcd0b-107">진행 함수의 형식 인수 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="bcd0b-107">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="bcd0b-108">진행 각각 함수의 형식 인수를 나타내는 ICorDebugType 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="bcd0b-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="bcd0b-109">첫 번째 요소는 반환 형식입니다. 다른 각 요소는 매개 변수 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bcd0b-109">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="bcd0b-110">제한이 함수에 대 한 포인터를 나타내는 개체의 주소에 대 한 포인터 `ICorDebugType` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bcd0b-110">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcd0b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bcd0b-111">Requirements</span></span>  

 <span data-ttu-id="bcd0b-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcd0b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcd0b-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcd0b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcd0b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcd0b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcd0b-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcd0b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

---
title: CloseCLREnumeration 함수
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
ms.openlocfilehash: 575e194cf952f02a3fe4fce9e955e45e1bc3653d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673915"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="f4827-102">CloseCLREnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="f4827-102">CloseCLREnumeration Function</span></span>

<span data-ttu-id="f4827-103">[EnumerateCLRs 함수](enumerateclrs-function.md)에서 반환 된 핸들 배열에 있는 모든 유효한 CLR (공용 언어 런타임) 계속 시작 이벤트를 닫고 핸들 및 문자열 경로 배열에 대 한 메모리를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4827-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4827-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4827-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4827-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f4827-105">Parameters</span></span>  

 `pHandleArray`  
 <span data-ttu-id="f4827-106">진행 [EnumerateCLRs 함수](enumerateclrs-function.md)에서 반환 된 이벤트 핸들 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f4827-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="f4827-107">진행 [EnumerateCLRs 함수](enumerateclrs-function.md)에서 반환 된 CLR 문자열 경로 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f4827-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="f4827-108">[in] `pHandleArray` 또는 `pStringArray`의 크기(길이)를 포함하는 DWORD입니다(동일).</span><span class="sxs-lookup"><span data-stu-id="f4827-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4827-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="f4827-109">Return Value</span></span>  

 <span data-ttu-id="f4827-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4827-110">S_OK</span></span>  
 <span data-ttu-id="f4827-111">[EnumerateCLRs 함수](enumerateclrs-function.md) 에 의해 열린 핸들이 닫히고 핸들 및 문자열 배열에 할당 된 메모리가 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4827-111">Handles opened by the [EnumerateCLRs function](enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="f4827-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f4827-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="f4827-113">`pHandleArray`의 길이가 `dwArrayLength`에 전달된 길이와 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f4827-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="f4827-114">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="f4827-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f4827-115">함수가 `pHandleArray` 및 `pStringArray`에 대한 메모리를 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4827-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4827-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4827-116">Requirements</span></span>  

 <span data-ttu-id="f4827-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4827-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4827-118">**헤더:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="f4827-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="f4827-119">**라이브러리:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="f4827-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="f4827-120">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="f4827-120">**.NET Framework Versions:** 3.5 SP1</span></span>

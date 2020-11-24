---
title: ICorDebugAppDomain::GetName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 501a4543940437bfe2a6cb0952aed8184107150c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672164"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="556d6-102">ICorDebugAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="556d6-102">ICorDebugAppDomain::GetName Method</span></span>

<span data-ttu-id="556d6-103">응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="556d6-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="556d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="556d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="556d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="556d6-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="556d6-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="556d6-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="556d6-107">이 메서드를 쿼리 모드로 전환 하려면이 값을 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="556d6-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="556d6-108">제한이 에서 실제로 반환 된 이름의 크기나 문자 수에 대 한 포인터입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="556d6-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="556d6-109">쿼리 모드에서이 값은 호출자가 이름에 할당할 버퍼의 크기를 알 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="556d6-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="556d6-110">제한이 응용 프로그램 도메인의 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="556d6-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="556d6-111">설명</span><span class="sxs-lookup"><span data-stu-id="556d6-111">Remarks</span></span>  

 <span data-ttu-id="556d6-112">디버거는 메서드를 `GetName` 한 번 호출 하 여 이름에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="556d6-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="556d6-113">디버거는 버퍼를 할당 한 다음 메서드를 두 번 호출 하 여 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="556d6-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="556d6-114">이름 크기를 가져오기 위한 첫 번째 호출은 *쿼리 모드* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="556d6-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="556d6-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="556d6-115">Requirements</span></span>  

 <span data-ttu-id="556d6-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="556d6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="556d6-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="556d6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="556d6-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="556d6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="556d6-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="556d6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

---
description: '자세히 알아보기: ICorDebugAppDomain:: GetName 메서드'
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
ms.openlocfilehash: 56995f544e1576534e35b899a659ed409972305f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772434"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="9c114-103">ICorDebugAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="9c114-103">ICorDebugAppDomain::GetName Method</span></span>

<span data-ttu-id="9c114-104">응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c114-104">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c114-105">구문</span><span class="sxs-lookup"><span data-stu-id="9c114-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c114-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c114-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="9c114-107">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9c114-107">[in] The size of the `szName` array.</span></span> <span data-ttu-id="9c114-108">이 메서드를 쿼리 모드로 전환 하려면이 값을 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c114-108">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9c114-109">제한이 에서 실제로 반환 된 이름의 크기나 문자 수에 대 한 포인터입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="9c114-109">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="9c114-110">쿼리 모드에서이 값은 호출자가 이름에 할당할 버퍼의 크기를 알 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c114-110">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="9c114-111">제한이 응용 프로그램 도메인의 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9c114-111">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c114-112">설명</span><span class="sxs-lookup"><span data-stu-id="9c114-112">Remarks</span></span>  

 <span data-ttu-id="9c114-113">디버거는 메서드를 `GetName` 한 번 호출 하 여 이름에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c114-113">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="9c114-114">디버거는 버퍼를 할당 한 다음 메서드를 두 번 호출 하 여 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="9c114-114">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="9c114-115">이름 크기를 가져오기 위한 첫 번째 호출은 *쿼리 모드* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c114-115">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c114-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c114-116">Requirements</span></span>  

 <span data-ttu-id="9c114-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c114-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c114-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c114-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c114-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c114-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c114-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c114-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

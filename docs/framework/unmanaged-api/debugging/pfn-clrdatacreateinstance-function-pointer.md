---
description: '자세한 정보: 함수 포인터 PFN_CLRDataCreateInstance'
title: PFN_CLRDataCreateInstance 함수 포인터
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
ms.openlocfilehash: fc048f840084eff0270944d3190ccbb153bf22d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800632"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a><span data-ttu-id="5b0d4-103">PFN_CLRDataCreateInstance 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="5b0d4-103">PFN_CLRDataCreateInstance Function Pointer</span></span>

<span data-ttu-id="5b0d4-104">지정 된 대상 항목에 대 한 인터페이스 개체를 만드는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="5b0d4-104">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0d4-105">구문</span><span class="sxs-lookup"><span data-stu-id="5b0d4-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b0d4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b0d4-106">Parameters</span></span>  

 `iid`  
 <span data-ttu-id="5b0d4-107">진행 인스턴스화할 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5b0d4-107">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="5b0d4-108">진행 인터페이스 개체를 만들 대상 항목을 나타내는 사용자 구현 [ICLRDataTarget](iclrdatatarget-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b0d4-108">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="5b0d4-109">제한이 반환 된 인터페이스 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b0d4-109">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b0d4-110">설명</span><span class="sxs-lookup"><span data-stu-id="5b0d4-110">Remarks</span></span>  

 <span data-ttu-id="5b0d4-111">`ICLRDataTarget`개체는 디버깅 응용 프로그램의 작성기에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b0d4-111">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="5b0d4-112">구현은 표시 되는 대상 항목의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="5b0d4-112">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="5b0d4-113">대상 항목은 프로세스, 메모리 덤프, 원격 컴퓨터 등 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b0d4-113">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b0d4-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b0d4-114">Requirements</span></span>  

 <span data-ttu-id="5b0d4-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b0d4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b0d4-116">**헤더:** ClrData .idl</span><span class="sxs-lookup"><span data-stu-id="5b0d4-116">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="5b0d4-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b0d4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b0d4-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b0d4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0d4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b0d4-119">See also</span></span>

- [<span data-ttu-id="5b0d4-120">디버깅 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5b0d4-120">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)

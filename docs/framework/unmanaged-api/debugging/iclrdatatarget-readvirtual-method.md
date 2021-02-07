---
description: '자세히 알아보기: ICLRDataTarget:: ReadVirtual 메서드'
title: ICLRDataTarget::ReadVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
ms.openlocfilehash: 740a89c95092cfad7974d6bc708c5d8b0d2a9172
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738205"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="e5b3a-103">ICLRDataTarget::ReadVirtual 메서드</span><span class="sxs-lookup"><span data-stu-id="e5b3a-103">ICLRDataTarget::ReadVirtual Method</span></span>

<span data-ttu-id="e5b3a-104">지정 된 가상 메모리 주소에서 지정 된 버퍼로 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e5b3a-104">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5b3a-105">구문</span><span class="sxs-lookup"><span data-stu-id="e5b3a-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5b3a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5b3a-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="e5b3a-107">진행 가상 메모리 주소를 저장 하는 CLRDATA_ADDRESS입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b3a-107">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="e5b3a-108">제한이 데이터를 받는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b3a-108">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="e5b3a-109">진행 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b3a-109">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="e5b3a-110">제한이 반환 된 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5b3a-110">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5b3a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5b3a-111">Requirements</span></span>  

 <span data-ttu-id="e5b3a-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5b3a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5b3a-113">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="e5b3a-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e5b3a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5b3a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5b3a-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b3a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b3a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5b3a-116">See also</span></span>

- [<span data-ttu-id="e5b3a-117">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5b3a-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)

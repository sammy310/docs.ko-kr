---
title: ICLRDataTarget::GetPointerSize 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
ms.openlocfilehash: 077aa50465d99c9098f26e67b3852feb0d399142
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703527"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="78550-102">ICLRDataTarget::GetPointerSize 메서드</span><span class="sxs-lookup"><span data-stu-id="78550-102">ICLRDataTarget::GetPointerSize Method</span></span>

<span data-ttu-id="78550-103">대상 프로세스에서 사용 하는 포인터 형식의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="78550-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="78550-104">이 메서드는 공용 언어 런타임 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78550-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78550-105">구문</span><span class="sxs-lookup"><span data-stu-id="78550-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78550-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78550-106">Parameters</span></span>  

 `pointerSize`  
 <span data-ttu-id="78550-107">제한이 대상 프로세스에 대 한 포인터의 크기 (바이트)를 지정 하는 정수 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="78550-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78550-108">설명</span><span class="sxs-lookup"><span data-stu-id="78550-108">Remarks</span></span>  

 <span data-ttu-id="78550-109">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="78550-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78550-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78550-110">Requirements</span></span>  

 <span data-ttu-id="78550-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78550-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78550-112">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="78550-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="78550-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78550-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78550-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78550-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78550-115">참조</span><span class="sxs-lookup"><span data-stu-id="78550-115">See also</span></span>

- [<span data-ttu-id="78550-116">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78550-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)

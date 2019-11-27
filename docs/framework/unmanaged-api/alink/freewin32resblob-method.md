---
title: FreeWin32ResBlob 메서드
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
ms.openlocfilehash: 2b1addc752c7238116e072c6e957d2b277ceb1e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449395"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="0af2c-102">FreeWin32ResBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="0af2c-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="0af2c-103">Win32 리소스 blob 및 관련 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0af2c-104">구문</span><span class="sxs-lookup"><span data-stu-id="0af2c-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0af2c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0af2c-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="0af2c-106">해제할 리소스 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-106">The resource blob to be released.</span></span> <span data-ttu-id="0af2c-107">이 메서드는 blob 포인터를 NULL에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0af2c-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="0af2c-108">Return Value</span></span>  
 <span data-ttu-id="0af2c-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0af2c-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0af2c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0af2c-110">Requirements</span></span>  
 <span data-ttu-id="0af2c-111">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="0af2c-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0af2c-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="0af2c-112">See also</span></span>

- [<span data-ttu-id="0af2c-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0af2c-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0af2c-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0af2c-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0af2c-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="0af2c-115">ALink API</span></span>](index.md)

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
ms.openlocfilehash: 44c5228f7ee467abd02a9ec09590d0352fc82036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684761"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="43f76-102">FreeWin32ResBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="43f76-102">FreeWin32ResBlob Method</span></span>

<span data-ttu-id="43f76-103">Win32 리소스 blob 및 관련 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="43f76-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43f76-104">구문</span><span class="sxs-lookup"><span data-stu-id="43f76-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="43f76-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43f76-105">Parameters</span></span>  

 `ppResBlob`  
 <span data-ttu-id="43f76-106">해제할 리소스 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="43f76-106">The resource blob to be released.</span></span> <span data-ttu-id="43f76-107">이 메서드는 blob 포인터를 NULL에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="43f76-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43f76-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="43f76-108">Return Value</span></span>  

 <span data-ttu-id="43f76-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43f76-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43f76-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43f76-110">Requirements</span></span>  

 <span data-ttu-id="43f76-111">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="43f76-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43f76-112">참조</span><span class="sxs-lookup"><span data-stu-id="43f76-112">See also</span></span>

- [<span data-ttu-id="43f76-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43f76-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="43f76-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43f76-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="43f76-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="43f76-115">ALink API</span></span>](index.md)

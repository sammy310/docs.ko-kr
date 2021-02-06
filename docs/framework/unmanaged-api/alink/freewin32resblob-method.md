---
description: '자세히 알아보기: FreeWin32ResBlob 메서드'
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
ms.openlocfilehash: 56c83632b623eec76e8e2d24030c79a8262f506f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637945"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="fe4ca-103">FreeWin32ResBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="fe4ca-103">FreeWin32ResBlob Method</span></span>

<span data-ttu-id="fe4ca-104">Win32 리소스 blob 및 관련 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe4ca-104">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe4ca-105">구문</span><span class="sxs-lookup"><span data-stu-id="fe4ca-105">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe4ca-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fe4ca-106">Parameters</span></span>  

 `ppResBlob`  
 <span data-ttu-id="fe4ca-107">해제할 리소스 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="fe4ca-107">The resource blob to be released.</span></span> <span data-ttu-id="fe4ca-108">이 메서드는 blob 포인터를 NULL에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe4ca-108">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe4ca-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="fe4ca-109">Return Value</span></span>  

 <span data-ttu-id="fe4ca-110">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe4ca-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe4ca-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe4ca-111">Requirements</span></span>  

 <span data-ttu-id="fe4ca-112">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="fe4ca-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4ca-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe4ca-113">See also</span></span>

- [<span data-ttu-id="fe4ca-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe4ca-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fe4ca-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe4ca-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="fe4ca-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="fe4ca-116">ALink API</span></span>](index.md)

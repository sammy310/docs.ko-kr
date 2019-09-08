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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea0fbceb1e778a2f26e0625a337b803f417b59eb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777254"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="7f429-102">FreeWin32ResBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="7f429-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="7f429-103">Win32 리소스 blob 및 관련 리소스를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f429-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f429-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f429-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f429-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f429-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="7f429-106">해제할 리소스 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="7f429-106">The resource blob to be released.</span></span> <span data-ttu-id="7f429-107">이 메서드는 blob 포인터를 NULL에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f429-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f429-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="7f429-108">Return Value</span></span>  
 <span data-ttu-id="7f429-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f429-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f429-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f429-110">Requirements</span></span>  
 <span data-ttu-id="7f429-111">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="7f429-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f429-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="7f429-112">See also</span></span>

- [<span data-ttu-id="7f429-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f429-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7f429-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f429-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7f429-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="7f429-115">ALink API</span></span>](index.md)

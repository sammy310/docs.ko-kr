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
ms.openlocfilehash: 75aec187452e2f9f442a5d4856fe6777c03f34c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741989"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="3af8e-102">FreeWin32ResBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="3af8e-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="3af8e-103">Win32 리소스 blob와 연결 된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="3af8e-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3af8e-104">구문</span><span class="sxs-lookup"><span data-stu-id="3af8e-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3af8e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3af8e-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="3af8e-106">출시 될 리소스 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="3af8e-106">The resource blob to be released.</span></span> <span data-ttu-id="3af8e-107">이 메서드는 NULL로 blob 포인터를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3af8e-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3af8e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3af8e-108">Return Value</span></span>  
 <span data-ttu-id="3af8e-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af8e-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3af8e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3af8e-110">Requirements</span></span>  
 <span data-ttu-id="3af8e-111">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="3af8e-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af8e-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="3af8e-112">See also</span></span>

- [<span data-ttu-id="3af8e-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3af8e-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3af8e-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3af8e-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3af8e-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="3af8e-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

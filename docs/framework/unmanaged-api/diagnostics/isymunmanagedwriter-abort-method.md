---
description: '자세히 알아보기: ISymUnmanagedWriter:: Abort 메서드'
title: ISymUnmanagedWriter::Abort 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Abort
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Abort
helpviewer_keywords:
- ISymUnmanagedWriter::Abort method [.NET Framework debugging]
- Abort method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 416b220f-38d4-48e0-bb49-d2faa7366702
topic_type:
- apiref
ms.openlocfilehash: 312694bf2b667ea78bf5ddc993d0e2b71c85a8ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762684"
---
# <a name="isymunmanagedwriterabort-method"></a><span data-ttu-id="aa449-103">ISymUnmanagedWriter::Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="aa449-103">ISymUnmanagedWriter::Abort Method</span></span>

<span data-ttu-id="aa449-104">기호를 기호 저장소에 커밋하지 않고 기호 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="aa449-104">Closes the symbol writer without committing the symbols to the symbol store.</span></span> <span data-ttu-id="aa449-105">이 호출 후에는 기호 작성기에서 추가 업데이트를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa449-105">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="aa449-106">기호를 커밋하고 기호 작성기를 닫으려면 [ISymUnmanagedWriter:: close](isymunmanagedwriter-close-method.md) 메서드를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa449-106">To commit the symbols and close the symbol writer, use the [ISymUnmanagedWriter::Close](isymunmanagedwriter-close-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa449-107">구문</span><span class="sxs-lookup"><span data-stu-id="aa449-107">Syntax</span></span>  
  
```cpp  
HRESULT Abort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="aa449-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="aa449-108">Return Value</span></span>  

 <span data-ttu-id="aa449-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="aa449-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa449-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa449-110">Requirements</span></span>  

 <span data-ttu-id="aa449-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="aa449-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa449-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa449-112">See also</span></span>

- [<span data-ttu-id="aa449-113">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa449-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

---
title: ISymUnmanagedWriter::CloseMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
ms.openlocfilehash: a6a6aa937078ed0627688a4eed3d9142a2e6e0ac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428099"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="839e1-102">ISymUnmanagedWriter::CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="839e1-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="839e1-103">현재 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="839e1-103">Closes the current method.</span></span> <span data-ttu-id="839e1-104">메서드를 닫은 후에는 더 이상 기호를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="839e1-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="839e1-105">구문</span><span class="sxs-lookup"><span data-stu-id="839e1-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="839e1-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="839e1-106">Return Value</span></span>  
 <span data-ttu-id="839e1-107">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="839e1-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="839e1-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="839e1-108">Requirements</span></span>  
 <span data-ttu-id="839e1-109">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="839e1-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="839e1-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="839e1-110">See also</span></span>

- [<span data-ttu-id="839e1-111">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="839e1-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="839e1-112">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="839e1-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)

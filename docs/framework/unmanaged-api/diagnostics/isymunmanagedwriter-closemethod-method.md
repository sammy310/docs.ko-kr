---
description: '자세히 알아보기: ISymUnmanagedWriter:: CloseMethod 메서드'
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
ms.openlocfilehash: 8d19de0827f94d52c92852b0d1f2b5567e109c15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762580"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="a5c73-103">ISymUnmanagedWriter::CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a5c73-103">ISymUnmanagedWriter::CloseMethod Method</span></span>

<span data-ttu-id="a5c73-104">현재 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c73-104">Closes the current method.</span></span> <span data-ttu-id="a5c73-105">메서드를 닫은 후에는 더 이상 기호를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c73-105">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5c73-106">구문</span><span class="sxs-lookup"><span data-stu-id="a5c73-106">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a5c73-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="a5c73-107">Return Value</span></span>  

 <span data-ttu-id="a5c73-108">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5c73-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5c73-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5c73-109">Requirements</span></span>  

 <span data-ttu-id="a5c73-110">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="a5c73-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c73-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5c73-111">See also</span></span>

- [<span data-ttu-id="a5c73-112">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5c73-112">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a5c73-113">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a5c73-113">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)

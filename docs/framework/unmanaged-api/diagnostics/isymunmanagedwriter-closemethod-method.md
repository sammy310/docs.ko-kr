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
ms.openlocfilehash: fcf250f10baf4c65cd1c8c918655e4b9f4f5cc4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731737"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="bd70a-102">ISymUnmanagedWriter::CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="bd70a-102">ISymUnmanagedWriter::CloseMethod Method</span></span>

<span data-ttu-id="bd70a-103">현재 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bd70a-103">Closes the current method.</span></span> <span data-ttu-id="bd70a-104">메서드를 닫은 후에는 더 이상 기호를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd70a-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd70a-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd70a-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bd70a-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="bd70a-106">Return Value</span></span>  

 <span data-ttu-id="bd70a-107">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="bd70a-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd70a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd70a-108">Requirements</span></span>  

 <span data-ttu-id="bd70a-109">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="bd70a-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd70a-110">참조</span><span class="sxs-lookup"><span data-stu-id="bd70a-110">See also</span></span>

- [<span data-ttu-id="bd70a-111">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd70a-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="bd70a-112">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="bd70a-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)

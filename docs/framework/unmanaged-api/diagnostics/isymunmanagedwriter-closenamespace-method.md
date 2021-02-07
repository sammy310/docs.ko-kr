---
description: '자세히 알아보기: ISymUnmanagedWriter:: CloseNamespace 메서드'
title: ISymUnmanagedWriter::CloseNamespace 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
ms.openlocfilehash: c552d8bc86ab2bbd93918fdd6be3f880b3d83178
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762567"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="8aecf-103">ISymUnmanagedWriter::CloseNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="8aecf-103">ISymUnmanagedWriter::CloseNamespace Method</span></span>

<span data-ttu-id="8aecf-104">가장 최근에 열린 네임 스페이스를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8aecf-104">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aecf-105">구문</span><span class="sxs-lookup"><span data-stu-id="8aecf-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8aecf-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="8aecf-106">Return Value</span></span>  

 <span data-ttu-id="8aecf-107">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8aecf-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aecf-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8aecf-108">Requirements</span></span>  

 <span data-ttu-id="8aecf-109">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8aecf-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aecf-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8aecf-110">See also</span></span>

- [<span data-ttu-id="8aecf-111">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aecf-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="8aecf-112">OpenNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="8aecf-112">OpenNamespace Method</span></span>](isymunmanagedwriter-opennamespace-method.md)

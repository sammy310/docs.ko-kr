---
title: ISymUnmanagedWriter::OpenNamespace 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: ab248c6a624fbed1a6783383566be093c449ff97
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609887"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="49b91-102">ISymUnmanagedWriter::OpenNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="49b91-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="49b91-103">새 네임스페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="49b91-103">Opens a new namespace.</span></span> <span data-ttu-id="49b91-104">네임 스페이스를 점유 하는 메서드나 변수를 정의 하기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="49b91-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="49b91-105">네임 스페이스는 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49b91-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49b91-106">구문</span><span class="sxs-lookup"><span data-stu-id="49b91-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49b91-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49b91-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="49b91-108">진행 새 네임 스페이스의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="49b91-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49b91-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="49b91-109">Return Value</span></span>  
 <span data-ttu-id="49b91-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="49b91-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49b91-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49b91-111">Requirements</span></span>  
 <span data-ttu-id="49b91-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="49b91-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b91-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49b91-113">See also</span></span>

- [<span data-ttu-id="49b91-114">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="49b91-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="49b91-115">CloseNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="49b91-115">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)

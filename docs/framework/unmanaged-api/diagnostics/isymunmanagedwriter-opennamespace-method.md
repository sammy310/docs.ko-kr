---
description: '자세히 알아보기: ISymUnmanagedWriter:: OpenNamespace 메서드'
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
ms.openlocfilehash: ab848e44dfda1f5caaa92bfd3376bdcbd67d8a9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762125"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="c4d54-103">ISymUnmanagedWriter::OpenNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="c4d54-103">ISymUnmanagedWriter::OpenNamespace Method</span></span>

<span data-ttu-id="c4d54-104">새 네임스페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c4d54-104">Opens a new namespace.</span></span> <span data-ttu-id="c4d54-105">네임 스페이스를 점유 하는 메서드나 변수를 정의 하기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d54-105">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="c4d54-106">네임 스페이스는 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d54-106">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4d54-107">구문</span><span class="sxs-lookup"><span data-stu-id="c4d54-107">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4d54-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4d54-108">Parameters</span></span>  

 `name`  
 <span data-ttu-id="c4d54-109">진행 새 네임 스페이스의 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4d54-109">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4d54-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="c4d54-110">Return Value</span></span>  

 <span data-ttu-id="c4d54-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c4d54-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4d54-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4d54-112">Requirements</span></span>  

 <span data-ttu-id="c4d54-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c4d54-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4d54-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4d54-114">See also</span></span>

- [<span data-ttu-id="c4d54-115">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c4d54-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="c4d54-116">CloseNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="c4d54-116">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)

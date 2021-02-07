---
description: '자세히 알아보기: ISymUnmanagedWriter:: Close 메서드'
title: ISymUnmanagedWriter::Close 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 02f4d8d4a232240160ad5065947282f40af42f4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762632"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="f8fe6-103">ISymUnmanagedWriter::Close 메서드</span><span class="sxs-lookup"><span data-stu-id="f8fe6-103">ISymUnmanagedWriter::Close Method</span></span>

<span data-ttu-id="f8fe6-104">기호를 기호 저장소에 커밋한 후 기호 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f8fe6-104">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8fe6-105">구문</span><span class="sxs-lookup"><span data-stu-id="f8fe6-105">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f8fe6-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="f8fe6-106">Return Value</span></span>  

 <span data-ttu-id="f8fe6-107">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f8fe6-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8fe6-108">설명</span><span class="sxs-lookup"><span data-stu-id="f8fe6-108">Remarks</span></span>  

 <span data-ttu-id="f8fe6-109">이 호출 후에는 기호 작성기에서 추가 업데이트를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8fe6-109">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="f8fe6-110">기호를 커밋하지 않고 기호 작성기를 닫으려면 [ISymUnmanagedWriter:: Abort](isymunmanagedwriter-abort-method.md) 메서드를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8fe6-110">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8fe6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8fe6-111">Requirements</span></span>  

 <span data-ttu-id="f8fe6-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="f8fe6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8fe6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8fe6-113">See also</span></span>

- [<span data-ttu-id="f8fe6-114">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8fe6-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

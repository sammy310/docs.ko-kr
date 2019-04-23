---
title: ISymENCUnmanagedMethod 인터페이스
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4474269688094ea6c81b06659727acfb9c2ad6c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095713"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="37f20-102">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37f20-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="37f20-103">편집 하며 계속 하기 기능에 대 한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37f20-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37f20-104">메서드</span><span class="sxs-lookup"><span data-stu-id="37f20-104">Methods</span></span>  
  
|<span data-ttu-id="37f20-105">메서드</span><span class="sxs-lookup"><span data-stu-id="37f20-105">Method</span></span>|<span data-ttu-id="37f20-106">설명</span><span class="sxs-lookup"><span data-stu-id="37f20-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37f20-107">GetDocumentsForMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="37f20-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="37f20-108">줄에는이 메서드는 문서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f20-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="37f20-109">GetDocumentsForMethodCount 메서드</span><span class="sxs-lookup"><span data-stu-id="37f20-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="37f20-110">줄에는이 메서드는 문서 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f20-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="37f20-111">GetFileNameFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="37f20-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="37f20-112">줄 오프셋을 사용 하 여 연결에 대 한 파일 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f20-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="37f20-113">GetLineFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="37f20-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="37f20-114">오프셋을 사용 하 여 연결 된 줄 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37f20-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="37f20-115">GetSourceExtentInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="37f20-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="37f20-116">최소 가져옵니다 특정 문서에서 줄 및 메서드에 대 한 가장 큰 끝 줄을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="37f20-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37f20-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37f20-117">Requirements</span></span>  
 <span data-ttu-id="37f20-118">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="37f20-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f20-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="37f20-119">See also</span></span>

- [<span data-ttu-id="37f20-120">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37f20-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

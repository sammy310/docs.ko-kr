---
title: ISymUnmanagedReader2 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: a07c75e14244fb5bdf72ff2b0d344ae27672ef89
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448273"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="5495f-102">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5495f-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="5495f-103">기호 저장소 내의 문서, 메서드 및 변수에 대 한 액세스를 제공 하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5495f-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="5495f-104">이 인터페이스는 [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5495f-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5495f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5495f-105">Methods</span></span>  
  
|<span data-ttu-id="5495f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5495f-106">Method</span></span>|<span data-ttu-id="5495f-107">설명</span><span class="sxs-lookup"><span data-stu-id="5495f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5495f-108">GetMethodByVersionPreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="5495f-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="5495f-109">메서드 토큰과 편집 하며 계속 하기 버전 번호가 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5495f-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="5495f-110">GetMethodsInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="5495f-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="5495f-111">제공 된 문서에서 줄 정보를 포함 하는 모든 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5495f-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="5495f-112">GetSymAttributePreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="5495f-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="5495f-113">이름에 따라 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5495f-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5495f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5495f-114">Requirements</span></span>  
 <span data-ttu-id="5495f-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="5495f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5495f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5495f-116">See also</span></span>

- [<span data-ttu-id="5495f-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5495f-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="5495f-118">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5495f-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

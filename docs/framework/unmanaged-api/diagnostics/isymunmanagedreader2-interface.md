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
ms.openlocfilehash: 3f34be833d3ccb5c636d2c5f18ccb6e216ef2c49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709078"
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="97b9a-102">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97b9a-102">ISymUnmanagedReader2 Interface</span></span>

<span data-ttu-id="97b9a-103">기호 저장소 내의 문서, 메서드 및 변수에 대한 액세스를 제공하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="97b9a-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="97b9a-104">이 인터페이스는 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="97b9a-104">This interface extends the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97b9a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="97b9a-105">Methods</span></span>  
  
|<span data-ttu-id="97b9a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="97b9a-106">Method</span></span>|<span data-ttu-id="97b9a-107">설명</span><span class="sxs-lookup"><span data-stu-id="97b9a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97b9a-108">GetMethodByVersionPreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="97b9a-108">GetMethodByVersionPreRemap Method</span></span>](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="97b9a-109">메서드 토큰과 편집 하며 계속 하기 버전 번호가 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97b9a-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="97b9a-110">GetMethodsInDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="97b9a-110">GetMethodsInDocument Method</span></span>](isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="97b9a-111">제공 된 문서에서 줄 정보를 포함 하는 모든 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97b9a-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="97b9a-112">GetSymAttributePreRemap 메서드</span><span class="sxs-lookup"><span data-stu-id="97b9a-112">GetSymAttributePreRemap Method</span></span>](isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="97b9a-113">이름에 따라 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97b9a-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="97b9a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97b9a-114">Requirements</span></span>  

 <span data-ttu-id="97b9a-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="97b9a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b9a-116">참조</span><span class="sxs-lookup"><span data-stu-id="97b9a-116">See also</span></span>

- [<span data-ttu-id="97b9a-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97b9a-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="97b9a-118">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97b9a-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

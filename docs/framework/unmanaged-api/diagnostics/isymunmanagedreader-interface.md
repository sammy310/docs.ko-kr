---
description: '자세히 알아보기: ISymUnmanagedReader 인터페이스'
title: ISymUnmanagedReader 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
ms.openlocfilehash: bad4fdbac3bf6f03fa0db79ce54a5b0ca897028f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763802"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="eb989-103">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb989-103">ISymUnmanagedReader Interface</span></span>

<span data-ttu-id="eb989-104">기호 저장소 내의 문서, 메서드 및 변수에 대한 액세스를 제공하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-104">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb989-105">메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-105">Methods</span></span>  
  
|<span data-ttu-id="eb989-106">메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-106">Method</span></span>|<span data-ttu-id="eb989-107">설명</span><span class="sxs-lookup"><span data-stu-id="eb989-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb989-108">GetDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-108">GetDocument Method</span></span>](isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="eb989-109">문서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-109">Finds a document.</span></span>|  
|[<span data-ttu-id="eb989-110">GetDocuments 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-110">GetDocuments Method</span></span>](isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="eb989-111">기호 저장소에 정의 된 모든 문서의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-111">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="eb989-112">GetDocumentVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-112">GetDocumentVersion Method</span></span>](isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="eb989-113">지정 된 문서의 지정 된 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-113">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="eb989-114">GetGlobalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-114">GetGlobalVariables Method</span></span>](isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="eb989-115">모든 전역 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-115">Returns all global variables.</span></span>|  
|[<span data-ttu-id="eb989-116">GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-116">GetMethod Method</span></span>](isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="eb989-117">메서드 토큰이 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-117">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="eb989-118">GetMethodByVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-118">GetMethodByVersion Method</span></span>](isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="eb989-119">메서드 토큰과 편집 및 복사 버전 번호가 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-119">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="eb989-120">GetMethodFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-120">GetMethodFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="eb989-121">문서의 지정 된 위치에 중단점을 포함 하는 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-121">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="eb989-122">GetMethodsFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-122">GetMethodsFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="eb989-123">각각 문서의 지정 된 위치에 중단점을 포함 하는 메서드의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-123">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="eb989-124">GetMethodVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-124">GetMethodVersion Method</span></span>](isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="eb989-125">메서드 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-125">Gets the method version.</span></span>|  
|[<span data-ttu-id="eb989-126">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-126">GetNamespaces Method</span></span>](isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="eb989-127">이 기호 저장소의 전역 범위에서 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-127">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="eb989-128">GetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-128">GetSymAttribute Method</span></span>](isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="eb989-129">이름에 따라 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-129">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="eb989-130">GetSymbolStoreFileName 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-130">GetSymbolStoreFileName Method</span></span>](isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="eb989-131">기호 저장소의 디스크에 있는 파일 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-131">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="eb989-132">GetUserEntryPoint 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-132">GetUserEntryPoint Method</span></span>](isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="eb989-133">모듈에 대 한 사용자 진입점으로 지정 된 메서드를 반환 합니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="eb989-133">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="eb989-134">GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-134">GetVariables Method</span></span>](isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="eb989-135">부모 및 이름이 지정 된 경우 지역 변수가 아닌 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-135">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="eb989-136">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-136">Initialize Method</span></span>](isymunmanagedreader-initialize-method.md)|<span data-ttu-id="eb989-137">이 판독기가 연결 될 메타 데이터 가져오기 인터페이스를 사용 하 여 기호 판독기를 모듈의 파일 이름과 함께 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-137">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="eb989-138">ReplaceSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-138">ReplaceSymbolStore Method</span></span>](isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="eb989-139">기존 기호 저장소를 델타 기호 저장소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-139">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="eb989-140">UpdateSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="eb989-140">UpdateSymbolStore Method</span></span>](isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="eb989-141">기존 기호 저장소를 델타 기호 저장소로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="eb989-141">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb989-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eb989-142">Requirements</span></span>  

 <span data-ttu-id="eb989-143">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="eb989-143">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb989-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb989-144">See also</span></span>

- [<span data-ttu-id="eb989-145">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb989-145">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="eb989-146">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eb989-146">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)

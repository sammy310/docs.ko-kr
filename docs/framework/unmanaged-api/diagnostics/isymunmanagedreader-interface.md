---
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
ms.openlocfilehash: 7ae978f5d2c9f7e90f4549c15a3935b441eabf04
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434001"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="871d7-102">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="871d7-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="871d7-103">기호 저장소 내의 문서, 메서드 및 변수에 대 한 액세스를 제공 하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="871d7-104">메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-104">Methods</span></span>  
  
|<span data-ttu-id="871d7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-105">Method</span></span>|<span data-ttu-id="871d7-106">설명</span><span class="sxs-lookup"><span data-stu-id="871d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="871d7-107">GetDocument 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-107">GetDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="871d7-108">문서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-108">Finds a document.</span></span>|  
|[<span data-ttu-id="871d7-109">GetDocuments 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-109">GetDocuments Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="871d7-110">기호 저장소에 정의 된 모든 문서의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="871d7-111">GetDocumentVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-111">GetDocumentVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="871d7-112">지정 된 문서의 지정 된 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="871d7-113">GetGlobalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-113">GetGlobalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="871d7-114">모든 전역 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="871d7-115">GetMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="871d7-116">메서드 토큰이 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="871d7-117">GetMethodByVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-117">GetMethodByVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="871d7-118">메서드 토큰과 편집 및 복사 버전 번호가 지정 된 경우 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="871d7-119">GetMethodFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-119">GetMethodFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="871d7-120">문서의 지정 된 위치에 중단점을 포함 하는 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="871d7-121">GetMethodsFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-121">GetMethodsFromDocumentPosition Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="871d7-122">각각 문서의 지정 된 위치에 중단점을 포함 하는 메서드의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="871d7-123">GetMethodVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-123">GetMethodVersion Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="871d7-124">메서드 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="871d7-125">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-125">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="871d7-126">이 기호 저장소의 전역 범위에서 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="871d7-127">GetSymAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-127">GetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="871d7-128">이름에 따라 사용자 지정 특성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="871d7-129">GetSymbolStoreFileName 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-129">GetSymbolStoreFileName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="871d7-130">기호 저장소의 디스크에 있는 파일 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="871d7-131">GetUserEntryPoint 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-131">GetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="871d7-132">모듈에 대 한 사용자 진입점으로 지정 된 메서드를 반환 합니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="871d7-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="871d7-133">GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-133">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="871d7-134">부모 및 이름이 지정 된 경우 지역 변수가 아닌 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="871d7-135">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-135">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|<span data-ttu-id="871d7-136">이 판독기가 연결 될 메타 데이터 가져오기 인터페이스를 사용 하 여 기호 판독기를 모듈의 파일 이름과 함께 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="871d7-137">ReplaceSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-137">ReplaceSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="871d7-138">기존 기호 저장소를 델타 기호 저장소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="871d7-139">UpdateSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="871d7-139">UpdateSymbolStore Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="871d7-140">기존 기호 저장소를 델타 기호 저장소로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="871d7-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="871d7-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="871d7-141">Requirements</span></span>  
 <span data-ttu-id="871d7-142">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="871d7-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="871d7-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="871d7-143">See also</span></span>

- [<span data-ttu-id="871d7-144">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="871d7-144">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="871d7-145">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="871d7-145">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)

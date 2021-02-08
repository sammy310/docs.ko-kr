---
description: '자세한 정보: 진단 기호 저장소 인터페이스'
title: 진단 기호 저장소 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
ms.openlocfilehash: 253a6e5eaa97c91332bca62f8fc47ad2945bf741
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800437"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="38784-103">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-103">Diagnostics Symbol Store Interfaces</span></span>

<span data-ttu-id="38784-104">이 항목에서는 컴파일러가 디버거에서 사용할 기호 정보를 생성할 수 있도록 하는 관리 되지 않는 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-104">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38784-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="38784-105">In This Section</span></span>  

 [<span data-ttu-id="38784-106">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-106">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="38784-107">실행 중인 응용 프로그램에 대 한 현재 바인딩 정보를 표시 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-107">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="38784-108">IDebugAutoAttach 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-108">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="38784-109">서버에서 호출 하는 디버거 자동 연결에 대 한 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-109">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="38784-110">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-110">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="38784-111">연결 알림 소스를 등록 및 등록 취소 하는 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-111">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="38784-112">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-112">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="38784-113">싱크 알림에 대 한 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-113">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="38784-114">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-114">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="38784-115">알림 필터를 설정 하는 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-115">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="38784-116">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-116">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="38784-117">편집 하며 계속 하기 기능에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-117">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="38784-118">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-118">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="38784-119">이 인터페이스는 [ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스](isymunmanagedasyncmethodpropertieswriter-interface.md)에 대 한 읽기 보수입니다.</span><span class="sxs-lookup"><span data-stu-id="38784-119">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="38784-120">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-120">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="38784-121">메서드 기호 당 선택적 비동기 메서드 정보를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38784-121">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="38784-122">는 열린 메서드와 함께 사용 해야 합니다. 즉, [Openmethod 메서드와](isymunmanagedwriter-openmethod-method.md) [closemethod 메서드](isymunmanagedwriter-closemethod-method.md)호출 사이에는를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-122">Must use with an opened method (that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="38784-123">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-123">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="38784-124">비관리 코드의 기호 바인더를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38784-124">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="38784-125">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-125">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="38784-126">비관리 코드에 대 한 기호 바인더를 나타내고 인터페이스를 확장 `ISymUnmanagedBinder` 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-126">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="38784-127">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-127">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="38784-128">비관리 코드에 대 한 기호 바인더를 나타내고 인터페이스를 확장 `ISymUnmanagedBinder` 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-128">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="38784-129">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-129">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="38784-130">관리 되지 않는 상수에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-130">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="38784-131">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-131">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="38784-132">관리 되지 않는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-132">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="38784-133">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-133">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="38784-134">기호 저장소가 참조하는 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38784-134">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="38784-135">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-135">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="38784-136">기호 저장소가 참조하는 문서에 쓰기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-136">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="38784-137">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-137">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="38784-138">편집 하며 계속 하기 기능을 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-138">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="38784-139">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-139">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="38784-140">기호 저장소 내의 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38784-140">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="38784-141">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-141">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="38784-142">네임스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38784-142">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="38784-143">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-143">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="38784-144">기호 저장소 내의 문서, 메서드 및 변수에 대한 액세스를 제공하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38784-144">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="38784-145">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-145">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="38784-146">메서드 토큰과 편집 및 복사 버전 번호를 지정 하 여 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38784-146">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="38784-147">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-147">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="38784-148">기호 검색 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-148">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="38784-149">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-149">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="38784-150">메서드 내의 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38784-150">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="38784-151">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-151">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="38784-152">메서드 내의 어휘 범위를 나타내고, `ISymUnmanagedScope` 범위 내에 정의 된 상수에 대 한 정보를 가져오는 메서드를 사용 하 여 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-152">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="38784-153">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-153">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="38784-154">모듈에 대 한 소스 서버 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-154">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="38784-155">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-155">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="38784-156">검색 경로에 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-156">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="38784-157">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-157">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="38784-158">매개 변수, 지역 변수 또는 필드와 같은 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38784-158">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="38784-159">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-159">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="38784-160">기호 작성기를 나타내며 문서, 시퀀스 포인트, 어휘 범위 및 변수를 정의하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-160">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="38784-161">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-161">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="38784-162">기호 작성기를 나타내며 문서, 시퀀스 포인트, 어휘 범위 및 변수를 정의하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-162">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="38784-163">인터페이스를 확장 `ISymUnmanagedWriter` 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-163">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="38784-164">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-164">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="38784-165">기호 작성기를 나타내며 문서, 시퀀스 포인트, 어휘 범위 및 변수를 정의하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-165">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="38784-166">인터페이스를 확장 `ISymUnmanagedWriter` 합니다.</span><span class="sxs-lookup"><span data-stu-id="38784-166">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="38784-167">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-167">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="38784-168">ISymUnmanagedWriter4 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="38784-168">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="38784-169">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38784-169">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="38784-170">ISymUnmanagedWriter5 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="38784-170">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="38784-171">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="38784-171">Related Sections</span></span>  

 [<span data-ttu-id="38784-172">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="38784-172">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="38784-173">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="38784-173">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="38784-174">디버깅</span><span class="sxs-lookup"><span data-stu-id="38784-174">Debugging</span></span>](../debugging/index.md)

---
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
ms.openlocfilehash: e376544a9d428ce5110a7e38b92a8e830f574664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725185"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="b0409-102">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-102">Diagnostics Symbol Store Interfaces</span></span>

<span data-ttu-id="b0409-103">이 항목에서는 컴파일러가 디버거에서 사용할 기호 정보를 생성할 수 있도록 하는 관리 되지 않는 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0409-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b0409-104">In This Section</span></span>  

 [<span data-ttu-id="b0409-105">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-105">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="b0409-106">실행 중인 응용 프로그램에 대 한 현재 바인딩 정보를 표시 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="b0409-107">IDebugAutoAttach 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-107">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="b0409-108">서버에서 호출 하는 디버거 자동 연결에 대 한 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="b0409-109">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-109">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="b0409-110">연결 알림 소스를 등록 및 등록 취소 하는 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="b0409-111">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-111">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="b0409-112">싱크 알림에 대 한 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="b0409-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="b0409-114">알림 필터를 설정 하는 메서드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="b0409-115">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="b0409-116">편집 하며 계속 하기 기능에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="b0409-117">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-117">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="b0409-118">이 인터페이스는 [ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스](isymunmanagedasyncmethodpropertieswriter-interface.md)에 대 한 읽기 보수입니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="b0409-119">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="b0409-120">메서드 기호 당 선택적 비동기 메서드 정보를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="b0409-121">는 열린 메서드와 함께 사용 해야 합니다. 즉, [Openmethod 메서드와](isymunmanagedwriter-openmethod-method.md) [closemethod 메서드](isymunmanagedwriter-closemethod-method.md)호출 사이에는를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="b0409-122">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-122">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="b0409-123">비관리 코드의 기호 바인더를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="b0409-124">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-124">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="b0409-125">비관리 코드에 대 한 기호 바인더를 나타내고 인터페이스를 확장 `ISymUnmanagedBinder` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="b0409-126">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-126">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="b0409-127">비관리 코드에 대 한 기호 바인더를 나타내고 인터페이스를 확장 `ISymUnmanagedBinder` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="b0409-128">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-128">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="b0409-129">관리 되지 않는 상수에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="b0409-130">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-130">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="b0409-131">관리 되지 않는 리소스를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="b0409-132">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-132">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="b0409-133">기호 저장소가 참조하는 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="b0409-134">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-134">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="b0409-135">기호 저장소가 참조하는 문서에 쓰기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="b0409-136">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-136">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="b0409-137">편집 하며 계속 하기 기능을 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="b0409-138">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-138">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="b0409-139">기호 저장소 내의 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="b0409-140">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-140">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="b0409-141">네임스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="b0409-142">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-142">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="b0409-143">기호 저장소 내의 문서, 메서드 및 변수에 대한 액세스를 제공하는 기호 판독기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="b0409-144">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-144">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="b0409-145">메서드 토큰과 편집 및 복사 버전 번호를 지정 하 여 기호 판독기 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="b0409-146">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="b0409-147">기호 검색 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="b0409-148">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-148">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="b0409-149">메서드 내의 어휘 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="b0409-150">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-150">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="b0409-151">메서드 내의 어휘 범위를 나타내고, `ISymUnmanagedScope` 범위 내에 정의 된 상수에 대 한 정보를 가져오는 메서드를 사용 하 여 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="b0409-152">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-152">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="b0409-153">모듈에 대 한 소스 서버 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="b0409-154">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="b0409-155">검색 경로에 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="b0409-156">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-156">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="b0409-157">매개 변수, 지역 변수 또는 필드와 같은 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="b0409-158">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-158">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="b0409-159">기호 작성기를 나타내며 문서, 시퀀스 포인트, 어휘 범위 및 변수를 정의하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="b0409-160">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="b0409-161">기호 작성기를 나타내며 문서, 시퀀스 포인트, 어휘 범위 및 변수를 정의하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="b0409-162">인터페이스를 확장 `ISymUnmanagedWriter` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="b0409-163">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-163">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="b0409-164">기호 작성기를 나타내며 문서, 시퀀스 포인트, 어휘 범위 및 변수를 정의하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="b0409-165">인터페이스를 확장 `ISymUnmanagedWriter` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="b0409-166">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-166">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="b0409-167">ISymUnmanagedWriter4 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="b0409-168">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b0409-168">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="b0409-169">ISymUnmanagedWriter5 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b0409-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b0409-170">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b0409-170">Related Sections</span></span>  

 [<span data-ttu-id="b0409-171">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="b0409-171">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="b0409-172">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="b0409-172">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="b0409-173">디버깅</span><span class="sxs-lookup"><span data-stu-id="b0409-173">Debugging</span></span>](../debugging/index.md)

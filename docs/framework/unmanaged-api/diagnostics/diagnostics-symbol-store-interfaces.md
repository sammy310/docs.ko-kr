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
ms.openlocfilehash: bdb691570a9a2bf7bd2bb21af500b06c10b0bc53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448531"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="15ad9-102">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="15ad9-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span><span class="sxs-lookup"><span data-stu-id="15ad9-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15ad9-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="15ad9-104">In This Section</span></span>  
 [<span data-ttu-id="15ad9-105">IBindingDisplay 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="15ad9-106">Provides methods that display current binding information about the running application.</span><span class="sxs-lookup"><span data-stu-id="15ad9-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="15ad9-107">IDebugAutoAttach 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="15ad9-108">Defines the interface for a server-invoked debugger auto attach.</span><span class="sxs-lookup"><span data-stu-id="15ad9-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="15ad9-109">INotifyConnection2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="15ad9-110">Declares methods for registering and unregistering a connection notification source.</span><span class="sxs-lookup"><span data-stu-id="15ad9-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="15ad9-111">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="15ad9-112">Declares methods for sink notification.</span><span class="sxs-lookup"><span data-stu-id="15ad9-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="15ad9-113">INotifySource2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="15ad9-114">Declares a method for setting notification filters.</span><span class="sxs-lookup"><span data-stu-id="15ad9-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="15ad9-115">ISymENCUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="15ad9-116">Provides information for the Edit and Continue feature.</span><span class="sxs-lookup"><span data-stu-id="15ad9-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="15ad9-117">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="15ad9-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="15ad9-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="15ad9-119">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="15ad9-120">Allows definition of optional async method information per method symbol.</span><span class="sxs-lookup"><span data-stu-id="15ad9-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="15ad9-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="15ad9-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="15ad9-122">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="15ad9-123">Represents a symbol binder for unmanaged code.</span><span class="sxs-lookup"><span data-stu-id="15ad9-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="15ad9-124">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="15ad9-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="15ad9-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="15ad9-126">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="15ad9-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span><span class="sxs-lookup"><span data-stu-id="15ad9-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="15ad9-128">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="15ad9-129">Provides access to unmanaged constants.</span><span class="sxs-lookup"><span data-stu-id="15ad9-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="15ad9-130">ISymUnmanagedDispose 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="15ad9-131">Disposes of unmanaged resources.</span><span class="sxs-lookup"><span data-stu-id="15ad9-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="15ad9-132">ISymUnmanagedDocument 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="15ad9-133">Represents a document referenced by a symbol store.</span><span class="sxs-lookup"><span data-stu-id="15ad9-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="15ad9-134">ISymUnmanagedDocumentWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="15ad9-135">Provides methods for writing to a document referenced by a symbol store.</span><span class="sxs-lookup"><span data-stu-id="15ad9-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="15ad9-136">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="15ad9-137">Provides methods for the Edit and Continue feature.</span><span class="sxs-lookup"><span data-stu-id="15ad9-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="15ad9-138">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="15ad9-139">Represents a method within the symbol store.</span><span class="sxs-lookup"><span data-stu-id="15ad9-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="15ad9-140">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="15ad9-141">Represents a namespace.</span><span class="sxs-lookup"><span data-stu-id="15ad9-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="15ad9-142">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="15ad9-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span><span class="sxs-lookup"><span data-stu-id="15ad9-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="15ad9-144">ISymUnmanagedReader2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="15ad9-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span><span class="sxs-lookup"><span data-stu-id="15ad9-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="15ad9-146">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="15ad9-147">Provides methods that get symbol search information.</span><span class="sxs-lookup"><span data-stu-id="15ad9-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="15ad9-148">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="15ad9-149">Represents a lexical scope within a method.</span><span class="sxs-lookup"><span data-stu-id="15ad9-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="15ad9-150">ISymUnmanagedScope2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="15ad9-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span><span class="sxs-lookup"><span data-stu-id="15ad9-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="15ad9-152">ISymUnmanagedSourceServerModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="15ad9-153">Provides source server data for a module.</span><span class="sxs-lookup"><span data-stu-id="15ad9-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="15ad9-154">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="15ad9-155">Provides methods that get information about the search path.</span><span class="sxs-lookup"><span data-stu-id="15ad9-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="15ad9-156">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="15ad9-157">Represents a variable, such as a parameter, a local variable, or a field.</span><span class="sxs-lookup"><span data-stu-id="15ad9-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="15ad9-158">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="15ad9-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="15ad9-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="15ad9-160">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="15ad9-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="15ad9-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="15ad9-162">Extends the `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="15ad9-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="15ad9-163">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="15ad9-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="15ad9-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="15ad9-165">Extends the `ISymUnmanagedWriter` interface.</span><span class="sxs-lookup"><span data-stu-id="15ad9-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="15ad9-166">ISymUnmanagedWriter4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="15ad9-167">ISymUnmanagedWriter4 interface.</span><span class="sxs-lookup"><span data-stu-id="15ad9-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="15ad9-168">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ad9-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="15ad9-169">ISymUnmanagedWriter5 interface.</span><span class="sxs-lookup"><span data-stu-id="15ad9-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="15ad9-170">관련 단원</span><span class="sxs-lookup"><span data-stu-id="15ad9-170">Related Sections</span></span>  
 [<span data-ttu-id="15ad9-171">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="15ad9-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="15ad9-172">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="15ad9-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="15ad9-173">디버깅</span><span class="sxs-lookup"><span data-stu-id="15ad9-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)

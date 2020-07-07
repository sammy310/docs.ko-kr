---
title: '방법: COM에서 .NET 형식 참조'
description: COM에서 .NET 형식을 참조합니다. VB 클라이언트는 개체 브라우저에서 .NET 개체를 볼 수 있지만 C++ 클라이언트는 \#import 지시어를 사용하여 TLB 파일을 참조해야 합니다.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
ms.openlocfilehash: f8d052c7b9bac9c4bab61ab1950e9e89a7c73912
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618963"
---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="7fa2b-104">방법: COM에서 .NET 형식 참조</span><span class="sxs-lookup"><span data-stu-id="7fa2b-104">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="7fa2b-105">클라이언트 및 서버 코드의 관점에서 COM과 .NET Framework의 차이점은 크게 눈에 띄지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2b-105">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="7fa2b-106">Microsoft Visual Basic 클라이언트는 개체 메서드와 구문, 속성 및 필드를 정확히 다른 COM 개체인 것처럼 노출하는 개체 브라우저에서 .NET 개체를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2b-106">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="7fa2b-107">동일한 도구를 사용하여 메타데이터를 COM 형식 라이브러리로 내보내지만 C++ 클라이언트의 경우 형식 라이브러리를 가져오는 프로세스가 약간 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2b-107">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="7fa2b-108">관리되지 않는 C++ 클라이언트에서 .NET 개체 멤버를 참조하려면 **#import** 지시문을 사용하여 TLB 파일(Tlbexp.exe로 생성됨)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2b-108">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="7fa2b-109">C++에서 형식 라이브러리를 참조할 경우 **raw_interfaces_only** 옵션을 지정하거나 기본 클래스 라이브러리 Mscorlib.tlb의 정의를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2b-109">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="7fa2b-110">라이브러리를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="7fa2b-110">To import a library</span></span>  
  
- <span data-ttu-id="7fa2b-111">**#import** 지시문에서 **raw_interfaces_only** 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2b-111">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="7fa2b-112">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="7fa2b-112">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="7fa2b-113">또는</span><span class="sxs-lookup"><span data-stu-id="7fa2b-113">-or-</span></span>  
  
- <span data-ttu-id="7fa2b-114">Mscorlib.tlb에 대한 #import 지시문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7fa2b-114">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="7fa2b-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="7fa2b-115">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7fa2b-116">참조</span><span class="sxs-lookup"><span data-stu-id="7fa2b-116">See also</span></span>

- [<span data-ttu-id="7fa2b-117">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="7fa2b-117">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="7fa2b-118">COM에 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="7fa2b-118">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="7fa2b-119">[.NET 개체 호출](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7fa2b-119">[Calling a .NET Object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100))</span></span>
- <span data-ttu-id="7fa2b-120">[COM 액세스를 위해 애플리케이션 배포](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7fa2b-120">[Deploying an Application for COM Access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100))</span></span>

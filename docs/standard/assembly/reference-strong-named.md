---
title: '방법: 강력한 이름의 어셈블리 참조'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: adda4ed2ab5c59e3518b8e724044529a79840ad0
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156480"
---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="40b0c-102">방법: 강력한 이름의 어셈블리 참조</span><span class="sxs-lookup"><span data-stu-id="40b0c-102">How to: Reference a strong-named assembly</span></span>
<span data-ttu-id="40b0c-103">강력한 이름의 어셈블리에서 형식이나 리소스를 참조하는 프로세스는 일반적으로 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-103">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="40b0c-104">컴파일 시간(초기 바인딩) 또는 런타임에 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-104">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
<span data-ttu-id="40b0c-105">컴파일 시간 참조는 컴파일할 어셈블리가 다른 어셈블리를 명시적으로 참조한다고 컴파일러에 표시할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-105">A compile-time reference occurs when you indicate to the compiler that the assembly to be compiled explicitly references another assembly.</span></span> <span data-ttu-id="40b0c-106">컴파일 시간 참조를 사용하는 경우 컴파일러가 대상으로 지정된 강력한 이름의 어셈블리의 공개 키를 자동으로 가져오고 컴파일되는 어셈블리의 어셈블리 참조에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-106">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40b0c-107">강력한 이름의 어셈블리는 다른 강력한 이름의 어셈블리에서 형식만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-107">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="40b0c-108">그러지 않으면 강력한 이름의 어셈블리 보안이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-108">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="40b0c-109">강력한 이름의 어셈블리에 대한 컴파일 시간 참조 만들기</span><span class="sxs-lookup"><span data-stu-id="40b0c-109">Make a compile-time reference to a strong-named assembly</span></span>  

<span data-ttu-id="40b0c-110">명령 프롬프트에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-110">At a command prompt, type the following command:</span></span>  

<span data-ttu-id="40b0c-111">\<*compiler command*>  **/reference:** \<*assembly name*></span><span class="sxs-lookup"><span data-stu-id="40b0c-111">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  

<span data-ttu-id="40b0c-112">이 명령에서 *compiler command*는 사용되는 언어의 컴파일러 명령이고, *assembly name*은 참조되는 어셈블리의 강력한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-112">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="40b0c-113">라이브러리 어셈블리를 만들기 위해 **/t:library** 옵션과 같은 다른 컴파일러 옵션을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-113">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  

<span data-ttu-id="40b0c-114">다음 예제에서는 *myLibAssembly.dll*이라는 강력한 이름의 어셈블리를 참조하는 *myAssembly.dll*이라는 어셈블리를 *myAssembly.cs*라는 코드 모듈에서 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-114">The following example creates an assembly called *myAssembly.dll* that references a strong-named assembly called *myLibAssembly.dll* from a code module called *myAssembly.cs*.</span></span>  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="40b0c-115">강력한 이름의 어셈블리에 대한 런타임 참조 만들기</span><span class="sxs-lookup"><span data-stu-id="40b0c-115">Make a run-time reference to a strong-named assembly</span></span>  
  
<span data-ttu-id="40b0c-116">강력한 이름의 어셈블리에 대한 런타임 참조를 만드는 경우(예: <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 또는 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> 메서드 사용), 참조되는 강력한 이름의 어셈블리의 표시 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-116">When you make a run-time reference to a strong-named assembly, for example by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> method, you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="40b0c-117">표시 이름의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-117">The syntax of a display name is as follows:</span></span>  

<span data-ttu-id="40b0c-118">\<*어셈블리 이름*> **,** \<*버전 번호*> **,** \<*문화권*> **,** \<*공개 키 토큰*></span><span class="sxs-lookup"><span data-stu-id="40b0c-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  

<span data-ttu-id="40b0c-119">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="40b0c-119">For example:</span></span>  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

<span data-ttu-id="40b0c-120">이 예제에서 `PublicKeyToken`은 16진수 형식의 공개 키 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-120">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="40b0c-121">문화권 값이 없는 경우 `Culture=neutral`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-121">If there is no culture value, use `Culture=neutral`.</span></span>  

<span data-ttu-id="40b0c-122">다음 코드 예제에서는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드와 함께 이 정보를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-122">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

<span data-ttu-id="40b0c-123">다음 [강력한 이름(Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) 명령을 사용하여 특정 어셈블리에 대한 공개 키와 공개 키 토큰의 16진수 형식을 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b0c-123">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  

<span data-ttu-id="40b0c-124">**sn -Tp \<** *어셈블리* **>**</span><span class="sxs-lookup"><span data-stu-id="40b0c-124">**sn -Tp \<** *assembly* **>**</span></span>  

<span data-ttu-id="40b0c-125">공개 키 파일이 있는 경우 다음 명령을 대신 사용할 수 있습니다(명령줄 옵션의 대/소문자 차이 확인).</span><span class="sxs-lookup"><span data-stu-id="40b0c-125">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  

<span data-ttu-id="40b0c-126">**sn -tp \<** *공개 키 파일* **>**</span><span class="sxs-lookup"><span data-stu-id="40b0c-126">**sn -tp \<** *public key file* **>**</span></span>  

## <a name="see-also"></a><span data-ttu-id="40b0c-127">참조</span><span class="sxs-lookup"><span data-stu-id="40b0c-127">See also</span></span>

- [<span data-ttu-id="40b0c-128">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="40b0c-128">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)

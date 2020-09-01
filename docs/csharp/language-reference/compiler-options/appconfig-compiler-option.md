---
description: -appconfig(C# 컴파일러 옵션)
title: -appconfig(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
ms.openlocfilehash: 287d41105199057add1dad78d480b083adb745b2
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126114"
---
# <a name="-appconfig-c-compiler-options"></a><span data-ttu-id="f54af-103">-appconfig(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f54af-103">-appconfig (C# Compiler Options)</span></span>
<span data-ttu-id="f54af-104">**-appconfig** 컴파일러 옵션을 사용하면 C# 애플리케이션이 어셈블리 바인딩 시간에 어셈블리의 애플리케이션 구성(app.config) 파일 위치를 CLR(공용 언어 런타임)에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-104">The **-appconfig** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f54af-105">구문</span><span class="sxs-lookup"><span data-stu-id="f54af-105">Syntax</span></span>  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="f54af-106">인수</span><span class="sxs-lookup"><span data-stu-id="f54af-106">Arguments</span></span>  
 `file`  
 <span data-ttu-id="f54af-107">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f54af-107">Required.</span></span> <span data-ttu-id="f54af-108">어셈블리 바인딩 설정이 포함된 애플리케이션 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-108">The application configuration file that contains assembly binding settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f54af-109">설명</span><span class="sxs-lookup"><span data-stu-id="f54af-109">Remarks</span></span>  
 <span data-ttu-id="f54af-110">**-appconfig**의 한 가지 용도는 어셈블리가 특정 참조 어셈블리의 .NET Framework 버전과 .NET Framework for Silverlight 버전을 동시에 둘 다 참조해야 하는 고급 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-110">One use of **-appconfig** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="f54af-111">예를 들어 WPF(Windows Presentation Foundation)로 작성된 XAML 디자이너는 디자이너의 사용자 인터페이스를 위한 WPF 데스크톱 및 Silverlight에 포함된 WPF 하위 집합을 둘 다 참조해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-111">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="f54af-112">같은 디자이너 어셈블리가 두 어셈블리에 모두 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-112">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="f54af-113">기본적으로, 어셈블리 바인딩 시 두 어셈블리가 동등한 것으로 간주되기 때문에 서로 다른 참조를 사용할 경우 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-113">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span>  
  
 <span data-ttu-id="f54af-114">**-appconfig** 컴파일러 옵션을 사용하면 다음 예제와 같이 `<supportPortability>` 태그를 사용하여 기본 동작을 비활성화하는 app.config 파일의 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-114">The **-appconfig** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 <span data-ttu-id="f54af-115">컴파일러는 이 파일 위치를 CLR의 어셈블리 바인딩 논리에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-115">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f54af-116">Microsoft Build Engine(MSBuild)을 사용하여 애플리케이션을 빌드하는 경우 .csproj 파일에 속성 태그를 추가하여 **-appconfig** 컴파일러 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-116">If you are using the Microsoft Build Engine (MSBuild) to build your application, you can set the **-appconfig** compiler option by adding a property tag to the .csproj file.</span></span> <span data-ttu-id="f54af-117">프로젝트에 이미 설정된 app.config 파일을 사용하려면 속성 태그 `<UseAppConfigForCompiler>`를 .csproj 파일에 추가하고 해당 값을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-117">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the .csproj file and set its value to `true`.</span></span> <span data-ttu-id="f54af-118">다른 app.config 파일을 지정하려면 속성 태그 `<AppConfigForCompiler>`를 추가하고 해당 값을 파일 위치로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-118">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f54af-119">예제</span><span class="sxs-lookup"><span data-stu-id="f54af-119">Example</span></span>  
 <span data-ttu-id="f54af-120">다음 예제에서는 애플리케이션이 두 구현에 모두 있는 .NET Framework 어셈블리의 .NET Framework for Silverlight 구현과 .NET Framework 구현 둘 다에 대한 참조를 사용할 수 있도록 하는 app.config 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-120">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="f54af-121">**-appconfig** 컴파일러 옵션은 이 app.config 파일의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f54af-121">The **-appconfig** compiler option specifies the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f54af-122">참조</span><span class="sxs-lookup"><span data-stu-id="f54af-122">See also</span></span>

- [<span data-ttu-id="f54af-123">\<supportPortability> 요소</span><span class="sxs-lookup"><span data-stu-id="f54af-123">\<supportPortability> Element</span></span>](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)
- [<span data-ttu-id="f54af-124">사전순 C# 컴파일러 옵션 목록</span><span class="sxs-lookup"><span data-stu-id="f54af-124">C# Compiler Options Listed Alphabetically</span></span>](./listed-alphabetically.md)

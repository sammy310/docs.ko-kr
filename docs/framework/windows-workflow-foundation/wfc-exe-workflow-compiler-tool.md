---
title: Wfc.exe (워크플로 명령줄 컴파일러 도구)
description: 워크플로 명령줄 컴파일러 도구인 wfc.exe를 이해 합니다.
ms.date: 10/10/2020
helpviewer_keywords:
- wfc [Workflow]
- compiler tool
- wfc.exe
- Workflow, compilation
- Workflow, XOML files
- Workflow, wcf
ms.openlocfilehash: 01cbfeb72e19f727a3a470059047a2192228c394
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293860"
---
# <a name="wfcexe-workflow-command-line-compiler-tool"></a><span data-ttu-id="56f7d-103">wfc.exe (워크플로 명령줄 컴파일러 도구)</span><span class="sxs-lookup"><span data-stu-id="56f7d-103">wfc.exe (Workflow Command-line Compiler Tool)</span></span>

> [!NOTE]
> <span data-ttu-id="56f7d-104">이 자료에서는 더 이상 사용되지 않는 형식과 네임스페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-104">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="56f7d-105">wfc.exe 워크플로 명령줄 컴파일러 도구는 파일 확장명이 *xoml* (사용 되지 않음) 인 이전 워크플로 마크업 파일에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-105">The wfc.exe workflow command-line compiler tool works with old workflow markup files that have the file extension *.xoml* (obsoleted).</span></span>

## <a name="compilation-process"></a><span data-ttu-id="56f7d-106">컴파일 프로세스</span><span class="sxs-lookup"><span data-stu-id="56f7d-106">Compilation process</span></span>

<span data-ttu-id="56f7d-107">워크플로가 컴파일될 때 다음 절차가 컴파일 프로세스의 일부로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-107">When workflows are compiled, the following procedures are performed as part of the compilation process:</span></span>

- <span data-ttu-id="56f7d-108">워크플로 활동이 자체적으로 설정된 규칙에 맞는지 확인하기 위해 유효성 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-108">Validation is performed to ensure that the workflow activities validate based on the rules that the activities have set for themselves.</span></span> <span data-ttu-id="56f7d-109">유효성 검사 오류가 발생하면 컴파일러에서 오류 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-109">If there are validation errors, the compiler returns a list of the errors.</span></span>  
- <span data-ttu-id="56f7d-110">컴파일러에 입력된 마크업 정의에서 partial 클래스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-110">A partial class is generated from the markup definition that is input into the compiler.</span></span>  

- <span data-ttu-id="56f7d-111">활동의 런타임 실행을 돕기 위해 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-111">Code is generated to help with the run-time execution of the activities.</span></span> <span data-ttu-id="56f7d-112">포함된 활동의 실행이 완료될 때 포함하는 활동에 알려주는 이벤트 구독이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-112">Event subscriptions are generated, which help activities know when the activities they contain are finished executing.</span></span>  
- <span data-ttu-id="56f7d-113">마크업 파일에서 생성된 partial 클래스와 코드 파일에서 생성된 partial 클래스가 .NET Framework C# 또는 Visual Basic 컴파일러에 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-113">The partial classes generated from the markup file and the partial classes from the code file are entered into the .NET Framework C# or Visual Basic compiler.</span></span> <span data-ttu-id="56f7d-114">이 프로세스의 출력은 .NET 어셈블리인 WorkflowSample.dll입니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-114">The output of this process is the .NET assembly, WorkflowSample.dll.</span></span> <span data-ttu-id="56f7d-115">이 파일을 배포하여 워크플로를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-115">This can be deployed to run the workflow.</span></span>

### <a name="compiler-options"></a><span data-ttu-id="56f7d-116">컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="56f7d-116">Compiler options</span></span>

<span data-ttu-id="56f7d-117">이 섹션에서는 wfc.exe 워크플로 명령줄 컴파일러에 대 한 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-117">This section shows the options for the wfc.exe workflow command-line compiler.</span></span>

```output
    Microsoft (R) Windows Workflow Compiler version 3.0.0.0
    Copyright (C) Microsoft Corporation 2005. All rights reserved.

                      Windows Workflow Compiler Options

    wfc.exe <Xoml file list> /target:assembly [<vb/cs file list>] [/language:...]
            [/out:...] [/reference:...] [/library:...] [/debug...] [/nocode...]
             [/checktypes...] [/resource:<resource info>]

                            - OUTPUT FILE -
    /out:<file>             Output file name
    /target:assembly        Build a Windows Workflow assembly (default).
                            Short form: /t:assembly
    /target:exe             Build a Windows Workflow application.
                            Short form: /t:exe
    /delaysign[+|-]         Delay-sign the assembly using only the public portion
                            of the strong name key.
    /keyfile:<file>         Specifies a strong name key file.
    /keycontainer:<string>  Specifies a strong name key container.

                            - INPUT FILES -
    <Xoml file list>        Xoml source file name(s).
    <vb/cs file list>       Code-beside file name(s).
    /reference:<file list>  Reference metadata from the specified assembly file(s).
                            Short form is '/r:'.
    /library:<path list>    Set of directories where to lookup for the references.
                            Short form is '/lib:'.
    /resource:<resinfo>     Embed the specified resource. Short form is '/res:'.
                            resinfo format is <file>[,<name>[,public|private]].

    Rules and freeform layout files must be embedded as assembly resources.
    The resource name is constructed by using the namespace and type name
    of the activity. For example, an activity named "MyActivity" in namespace
    "WFProject" would require resource names "WFProject.MyActivity.rules"
    and/or "WFProject.MyActivity.layout".

                            - CODE GENERATION -
    /debug[+|-]             Emit full debugging information. The default is '+'.
    /nocode[+|-]            Disallow code-beside model.
                            The default is '-'. Short form is '/nc:'.
    /checktypes[+|-]        Check for permitted types in wfc.exe.config file.
                            The default is '-'. Short form is '/ct:'.

                            - LANGUAGE -
    /language:[cs|vb]       The language to use for the generated class.
                            The default is 'CS' (C#). Short form is '/l:'.
    /rootnamespace:<string> Specifies the root Namespace for all type declarations.
                            Valid only for 'VB' (Visual Basic) language.
                            Short form is '/rns:'.

                            - MISCELLANEOUS -
    /help                   Display this usage message. Short form is '/?'.
    /nologo                 Suppress compiler copyright message. Short form is '/n'.

    /nowarn                 Ignore compiler warnings. Short form is '/w'.
```

## <a name="remarks"></a><span data-ttu-id="56f7d-118">설명</span><span class="sxs-lookup"><span data-stu-id="56f7d-118">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="56f7d-119">이 자료에서는 더 이상 사용되지 않는 형식과 네임스페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-119">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="56f7d-120">권한 있는 형식 목록은 일반적으로 *wfc.exe.config* 파일에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-120">A list of authorized types is usually defined in the *wfc.exe.config* file.</span></span> <span data-ttu-id="56f7d-121">워크플로 컴파일의 유효성 검사 단계 중에 워크플로 소스 문서가 거부 됩니다. 또는 동반 규칙 파일이 권한이 부여 된 형식 목록에 없는 .NET Framework 형식을 직접 참조 하는 경우</span><span class="sxs-lookup"><span data-stu-id="56f7d-121">During the validation phase of workflow compilation, a workflow source document is rejected if it or the companion rules file directly references any .NET Framework types not present in a list of authorized types.</span></span> <span data-ttu-id="56f7d-122">권한이 부여 된 형식 목록은 XML 문서 각 항목을 `Assembly`, `Namespace`, `TypeName`, 및 Authorized {`True`&#124;`False`} 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-122">The list of authorized types is an XML document where each entry indicates an `Assembly`, a `Namespace`, a `TypeName`, and an Authorized {`True`&#124;`False`} indicator.</span></span> <span data-ttu-id="56f7d-123">`AuthorizedType` 목록의 항목에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-123">`AuthorizedType` corresponds to an entry in the list.</span></span> <span data-ttu-id="56f7d-124">전체 네임 스페이스를 포함 하거나 제외 하는 데 사용할 수 있는 와일드 카드 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-124">Wildcard character designations, which can be used to include or exclude complete namespaces, are allowed.</span></span> <span data-ttu-id="56f7d-125">예를 들어에는 `Type="System.*"` <xref:System> 자식 네임 스페이스에 포함 된 형식을 포함 하 여의 모든 형식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-125">For example, `Type="System.*"` includes all types in <xref:System>, including types contained in child namespaces.</span></span>
  
<span data-ttu-id="56f7d-126">권한이 부여 된 형식 목록의 사용은 옵션에 의해 제어 됩니다 <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> `'/checktypes'` .</span><span class="sxs-lookup"><span data-stu-id="56f7d-126">The use of a list of authorized types is controlled by the <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> option `'/checktypes'`.</span></span>

```xml  
<configuration>  
  <System.Workflow.ComponentModel.WorkflowCompiler>
    <authorizedTypes>
      <targetFx version="v4.0">
        ...
        <authorizedType Assembly="System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True"/>
        ...
      </targetFx>
    </authorizedTypes>
  </System.Workflow.ComponentModel.WorkflowCompiler>  
</configuration>  
```

> [!WARNING]
> <span data-ttu-id="56f7d-127">`Type="System.*"`형식이 있는 경우 컴파일에 사용할 다른 의도 하지 않은 형식 (예:)을 포함할 수 있습니다 `Type="System.Configuration"` .</span><span class="sxs-lookup"><span data-stu-id="56f7d-127">When `Type="System.*"` type is present, it's possible to include other unintended types, such as `Type="System.Configuration"`, for compilation.</span></span> <span data-ttu-id="56f7d-128">신중 하 게 검토 하 고 각 항목을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-128">You should be cautious and review each one.</span></span> <span data-ttu-id="56f7d-129">제한 되어야 하는 모든 형식에 대해를로 설정 해야 `Authorized` `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="56f7d-129">For any type that should be restricted, be sure to set `Authorized` to `False`.</span></span>

## <a name="see-also"></a><span data-ttu-id="56f7d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56f7d-130">See also</span></span>

- [<span data-ttu-id="56f7d-131">AuthorizedType 클래스</span><span class="sxs-lookup"><span data-stu-id="56f7d-131">AuthorizedType class</span></span>](xref:System.Workflow.ComponentModel.Compiler.AuthorizedType)

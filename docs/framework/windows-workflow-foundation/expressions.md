---
title: 식-WF
ms.date: 03/30/2017
ms.assetid: c42341a9-43a1-462c-bffb-c5de004aa428
ms.openlocfilehash: 62b278825de6242075e89e3b243b6d6d8ef4d599
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306202"
---
# <a name="expressions"></a><span data-ttu-id="a711c-102">표현식</span><span class="sxs-lookup"><span data-stu-id="a711c-102">Expressions</span></span>

<span data-ttu-id="a711c-103">WF (Windows Workflow Foundation) 식은 결과를 반환 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-103">A Windows Workflow Foundation (WF) expression is any activity that returns a result.</span></span> <span data-ttu-id="a711c-104">모든 식 활동은 활동의 반환 값으로 <xref:System.Activities.Activity%601>라는 <xref:System.Activities.OutArgument> 속성을 포함하는 <xref:System.Activities.Activity%601.Result%2A>에서 간접적으로 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-104">All expression activities derive indirectly from <xref:System.Activities.Activity%601>, which contains an <xref:System.Activities.OutArgument> property named <xref:System.Activities.Activity%601.Result%2A> as the activity’s return value.</span></span> [!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="a711c-105">는 연산자 활동을 통해 단일 워크플로 변수에 대한 액세스를 제공하는 <xref:System.Activities.Expressions.VariableValue%601> 및 <xref:System.Activities.Expressions.VariableReference%601> 등의 단순한 활동부터 결과를 생성하기 위해 전체 Visual Basic 언어에 대한 액세스를 제공하는 <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> 및 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> 등의 복잡한 활동까지 광범위한 식 활동과 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-105">ships with a wide range of expression activities from simple ones like <xref:System.Activities.Expressions.VariableValue%601> and <xref:System.Activities.Expressions.VariableReference%601>, which provide access to single workflow variable through operator activities, to complex activities such as <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> that offer access to the full breadth of Visual Basic language to produce the result.</span></span> <span data-ttu-id="a711c-106"><xref:System.Activities.CodeActivity%601> 또는 <xref:System.Activities.NativeActivity%601>에서 파생시켜서 추가 식 활동을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-106">Additional expression activities can be created by deriving from <xref:System.Activities.CodeActivity%601> or <xref:System.Activities.NativeActivity%601>.</span></span>

## <a name="using-expressions"></a><span data-ttu-id="a711c-107">식 사용</span><span class="sxs-lookup"><span data-stu-id="a711c-107">Using Expressions</span></span>
 <span data-ttu-id="a711c-108">워크플로 디자이너에서는 Visual Basic 프로젝트의 모든 식에 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> 및 <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601>를 사용하며, C# 워크플로 프로젝트에는 <xref:Microsoft.CSharp.Activities.CSharpValue%601> 및 <xref:Microsoft.CSharp.Activities.CSharpReference%601>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-108">Workflow designer uses <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> for all expressions in Visual Basic projects, and <xref:Microsoft.CSharp.Activities.CSharpValue%601> and <xref:Microsoft.CSharp.Activities.CSharpReference%601> for expressions in C# workflow projects.</span></span>

> [!NOTE]
> <span data-ttu-id="a711c-109">워크플로 프로젝트 C# 의 식에 대 한 지원은 .NET Framework 4.5에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-109">Support for C# expressions in workflow projects was introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="a711c-110">자세한 내용은 [ C# 식](csharp-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a711c-110">For more information, see [C# Expressions](csharp-expressions.md).</span></span>

 <span data-ttu-id="a711c-111">디자이너에서 생성된 워크플로는 XAML로 저장됩니다. 여기서 식은 다음 예와 같이 대괄호로 묶인 상태로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-111">Workflows produced by designer are saved in XAML, where expressions appear enclosed in square brackets, as in the following example.</span></span>

```xml
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <Sequence.Variables>
    <Variable x:TypeArguments="x:Int32" Default="1" Name="a" />
    <Variable x:TypeArguments="x:Int32" Default="2" Name="b" />
    <Variable x:TypeArguments="x:Int32" Default="3" Name="c" />
    <Variable x:TypeArguments="x:Int32" Default="0" Name="r" />
  </Sequence.Variables>
  <Assign>
    <Assign.To>
      <OutArgument x:TypeArguments="x:Int32">[r]</OutArgument>
    </Assign.To>
    <Assign.Value>
      <InArgument x:TypeArguments="x:Int32">[a + b + c]</InArgument>
    </Assign.Value>
  </Assign>
</Sequence>
```

 <span data-ttu-id="a711c-112">코드에서 워크플로를 정의하면 모든 식 활동을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-112">When defining a workflow in code, any expression activities can be used.</span></span> <span data-ttu-id="a711c-113">다음 예에서는 연산자 활동의 컴퍼지션을 사용 하 여 세 개의 숫자를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-113">The following example shows the usage of a composition of operator activities to add three numbers:</span></span>

```csharp
Variable<int> a = new Variable<int>("a", 1);
Variable<int> b = new Variable<int>("b", 2);
Variable<int> c = new Variable<int>("c", 3);
Variable<int> r = new Variable<int>("r", 0);

Sequence w = new Sequence
{
    Variables = { a, b, c, r },
    Activities =
    {
        new Assign {
            To = new OutArgument<int>(r),
            Value = new InArgument<int> {
                Expression = new Add<int, int, int> {
                    Left = new Add<int, int, int> {
                        Left = new InArgument<int>(a),
                        Right = new InArgument<int>(b)
                    },
                    Right = new InArgument<int>(c)
                }
            }
        }
    }
};
```

 <span data-ttu-id="a711c-114">다음 예제와 같이 람다 식을 사용 하 C# 여 동일한 워크플로를 더 조밀 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-114">The same workflow can be expressed more compactly by using C# lambda expressions, as shown in the following example:</span></span>
  
```csharp
Variable<int> a = new Variable<int>("a", 1);
Variable<int> b = new Variable<int>("b", 2);
Variable<int> c = new Variable<int>("c", 3);
Variable<int> r = new Variable<int>("r", 0);

Sequence w = new Sequence
{
    Variables = { a, b, c, r },
    Activities = 
    {
        new Assign {
            To = new OutArgument<int>(r),
            Value = new InArgument<int>((ctx) => a.Get(ctx) + b.Get(ctx) + c.Get(ctx))
        }
    }
};
```

## <a name="extending-available-expressions-with-custom-expression-activities"></a><span data-ttu-id="a711c-115">사용자 지정 식 활동을 사용하여 사용 가능한 식 확장</span><span class="sxs-lookup"><span data-stu-id="a711c-115">Extending Available Expressions with Custom Expression Activities</span></span>

 <span data-ttu-id="a711c-116">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]의 식을 확장하여 추가 식 활동을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-116">Expressions in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are extensible allowing for additional expression activities to be created.</span></span> <span data-ttu-id="a711c-117">다음 예에서는 정수 값 세 개의 합을 반환하는 활동을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-117">The following example shows an activity that returns a sum of three integer values.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Activities;

namespace ExpressionsDemo
{
    public sealed class AddThreeValues : CodeActivity<int>
    {
        public InArgument<int> Value1 { get; set; }
        public InArgument<int> Value2 { get; set; }
        public InArgument<int> Value3 { get; set; }

        protected override int Execute(CodeActivityContext context)
        {
            return Value1.Get(context) +
                   Value2.Get(context) +
                   Value3.Get(context);
        }
    }
}
```

 <span data-ttu-id="a711c-118">이 새 활동을 사용 하면 다음 예제와 같이 세 개의 값을 추가한 이전 워크플로를 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a711c-118">With this new activity you can rewrite the previous workflow that added three values as shown in the following example:</span></span>

```csharp
Variable<int> a = new Variable<int>("a", 1);
Variable<int> b = new Variable<int>("b", 2);
Variable<int> c = new Variable<int>("c", 3);
Variable<int> r = new Variable<int>("r", 0);

Sequence w = new Sequence
{
    Variables = { a, b, c, r },
    Activities =
    {
        new Assign {
            To = new OutArgument<int>(r),
            Value = new InArgument<int> {
                Expression = new AddThreeValues() {
                    Value1 = new InArgument<int>(a),
                    Value2 = new InArgument<int>(b),
                    Value3 = new InArgument<int>(c)
                }
            }
        }
    }
};
```

 <span data-ttu-id="a711c-119">코드에서 식을 사용 하는 방법에 대 한 자세한 내용은 [명령적 코드를 사용 하 여 워크플로, 활동 및 식 작성](authoring-workflows-activities-and-expressions-using-imperative-code.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a711c-119">For more information about using expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

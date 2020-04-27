---
title: '방법: MetadataLoadContext를 사용하여 어셈블리 콘텐츠 검사'
description: 검사 목적으로 .NET 어셈블리를 로드할 수 있는 API인 MetadataLoadContext를 사용하는 방법을 알아봅니다.
author: MSDN-WhiteKnight
ms.date: 03/10/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 90c84147c52199afc42a2efc297bc7fe40658ec7
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141194"
---
# <a name="how-to-inspect-assembly-contents-using-metadataloadcontext"></a>방법: MetadataLoadContext를 사용하여 어셈블리 콘텐츠 검사

개발자는 기본적으로 .NET의 리플렉션 API를 통해 주 실행 컨텍스트에 로드된 어셈블리의 콘텐츠를 검사할 수 있습니다. 그러나 예를 들어 다른 플랫폼 또는 프로세서 아키텍처에 대해 컴파일되었거나 [참조 어셈블리](reference-assemblies.md)이기 때문에 어셈블리를 실행 컨텍스트에 로드하지 못할 수도 있습니다. <xref:System.Reflection.MetadataLoadContext?displayProperty=fullName> API를 사용하여 이러한 어셈블리를 로드하고 검사할 수 있습니다. <xref:System.Reflection.MetadataLoadContext>에 로드된 어셈블리는 메타데이터로만 처리됩니다. 즉, 어셈블리의 형식을 검사할 수 있지만 여기에 포함된 코드를 실행할 수는 없습니다. 주 실행 컨텍스트와 달리 <xref:System.Reflection.MetadataLoadContext>는 현재 디렉터리에서 종속성을 자동으로 로드하지 않고, 전달된 <xref:System.Reflection.MetadataAssemblyResolver>에서 제공하는 사용자 지정 바인딩 논리를 대신 사용합니다.

## <a name="prerequisites"></a>사전 요구 사항

<xref:System.Reflection.MetadataLoadContext>를 사용하려면 [MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext) NuGet 패키지를 설치합니다. 모든 .NET Standard 2.0 규격 대상 프레임워크(예: .NET Core 2.0 또는 .NET Framework 4.6.1)에서 지원됩니다.

## <a name="create-metadataassemblyresolver-for-metadataloadcontext"></a>MetadataLoadContext용 MetadataAssemblyResolver 만들기

<xref:System.Reflection.MetadataLoadContext>를 만들려면 <xref:System.Reflection.MetadataAssemblyResolver> 인스턴스를 제공해야 합니다. 이를 제공하는 가장 간단한 방법은 지정된 어셈블리 경로 문자열 컬렉션에서 어셈블리를 확인하는 <xref:System.Reflection.PathAssemblyResolver>를 사용하는 것입니다. 이 컬렉션은 직접 검사하려는 어셈블리 외에도 필요한 모든 종속성을 포함해야 합니다. 예를 들어 외부 어셈블리에 있는 사용자 지정 특성을 읽으려면 해당 어셈블리를 포함해야 합니다. 그렇지 않으면 예외가 throw됩니다. 대부분의 경우 *핵심 어셈블리*, 즉 <xref:System.Object?displayProperty=nameWithType> 같은 기본 제공 시스템 형식을 포함하는 어셈블리를 포함해야 합니다. 다음 코드에서는 검사된 어셈블리 및 현재 런타임의 핵심 어셈블리로 구성된 컬렉션을 사용하여 <xref:System.Reflection.PathAssemblyResolver>를 만드는 방법을 보여 줍니다.

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CoreAssembly)]

모든 BCL 형식에 액세스해야 하는 경우 컬렉션에 모든 런타임 어셈블리를 포함할 수 있습니다. 다음 코드에서는 검사된 어셈블리 및 현재 런타임의 모든 어셈블리로 구성된 컬렉션을 사용하여 <xref:System.Reflection.PathAssemblyResolver>를 만드는 방법을 보여 줍니다.

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#RuntimeAssemblies)]

## <a name="create-metadataloadcontext"></a>MetadataLoadContext 만들기

<xref:System.Reflection.MetadataLoadContext>를 만들려면 이전에 만든 <xref:System.Reflection.MetadataAssemblyResolver>를 첫 번째 매개 변수로 전달하고 핵심 어셈블리 이름을 두 번째 매개 변수로 전달하여 생성자 <xref:System.Reflection.MetadataLoadContext.%23ctor%28System.Reflection.MetadataAssemblyResolver%2CSystem.String%29>를 호출합니다. 핵심 어셈블리 이름을 생략할 수 있습니다. 이 경우 생성자는 기본 이름인 "mscorlib", "System.webserver" 또는 "netstandard"를 사용합니다.

컨텍스트를 만든 후 <xref:System.Reflection.MetadataLoadContext.LoadFromAssemblyPath%2A>와 같은 메서드를 사용하여 어셈블리를 로드할 수 있습니다. 코드 실행과 관련된 어셈블리를 제외하고 로드된 어셈블리에서 모든 리플렉션 API를 사용할 수 있습니다. <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A> 메서드는 생성자 실행과 관련되므로 <xref:System.Reflection.MetadataLoadContext>에서 사용자 지정 특성을 검사해야 하는 경우 대신 <xref:System.Reflection.MemberInfo.GetCustomAttributesData%2A> 메서드를 사용합니다.

다음 코드 샘플에서는 <xref:System.Reflection.MetadataLoadContext>를 만들고, 어셈블리를 로드하고, 어셈블리 특성을 콘솔에 출력합니다.

[!code-csharp[](snippets/inspect-contents-using-metadataloadcontext/MetadataLoadContextSnippets.cs#CreateContext)]

## <a name="example"></a>예제

전체 코드 예제를 보려면 [MetadataLoadContext 샘플을 사용하여 어셈블리 콘텐츠 검사](https://docs.microsoft.com/samples/dotnet/samples/inspect-assembly-contents-using-metadataloadcontext/)를 참조하세요.

---
title: 종속성 로딩 - .NET Core
description: .NET Core에서 관리 및 관리되지 않는 종속성 로드 개요
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.topic: overview
ms.openlocfilehash: 2eaa01fad3913272dc90891592d0e35cd89ad2ab
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506320"
---
# <a name="dependency-loading-in-net-core"></a>.NET Core에서 종속성 로딩

모든 .NET Core 애플리케이션에는 종속성이 있습니다. 간단한 `hello world` 앱에도 .NET Core 클래스 라이브러리의 일부에 대한 종속성이 있습니다.

.NET Core 기본 어셈블리 로드 논리를 이해하면 일반적인 배포 문제를 이해하고 디버깅할 수 있습니다.

일부 애플리케이션에서 종속성은 런타임에 동적으로 결정됩니다. 이러한 경우 관리 어셈블리 및 관리되지 않는 종속성이 로드되는 방식을 이해하는 것이 중요합니다.

## <a name="understanding-assemblyloadcontext"></a>AssemblyLoadContext 이해

<xref:System.Runtime.Loader.AssemblyLoadContext> API는 .NET Core 로딩 디자인의 핵심입니다. [AssemblyLoadContext 이해](understanding-assemblyloadcontext.md) 문서는 디자인에 대한 개념적 개요를 제공합니다.

## <a name="loading-details"></a>세부 정보를 로드하는 중

로드 알고리즘 세부 정보는 다음과 같은 여러 문서에서 간략하게 설명합니다.

- [관리 어셈블리 로드 알고리즘](loading-managed.md)
- [위성 어셈블리 로드 알고리즘](loading-resources.md)
- [관리되지 않는(네이티브) 라이브러리 로드 알고리즘](loading-unmanaged.md)
- [기본 검색](default-probing.md)

## <a name="create-a-net-core-application-with-plugins"></a>플러그 인을 사용하여 .NET Core 애플리케이션 만들기

자습서 [플러그 인을 사용하여 .NET Core 애플리케이션 만들기](../tutorials/creating-app-with-plugin-support.md)에서는 사용자 지정 AssemblyLoadContext를 만드는 방법을 설명합니다. <xref:System.Runtime.Loader.AssemblyDependencyResolver>를 사용하여 플러그 인의 종속성을 확인합니다. 이 자습서에서는 플러그 인의 종속성을 호스팅 애플리케이션에서 올바르게 격리합니다.

## <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>.NET Core에서 어셈블리 언로드 기능을 사용하고 디버그하는 방법

[.NET Core에서 어셈블리 언로드 기능을 사용하고 디버그하는 방법](../../standard/assembly/unloadability.md) 문서는 단계별 자습서입니다. .NET Core 애플리케이션을 로드하고 실행한 다음, 언로드하는 방법을 보여 줍니다. 이 문서는 디버깅 팁도 제공합니다.

## <a name="collect-detailed-assembly-loading-information"></a>자세한 어셈블리 로딩 정보 수집

[자세한 어셈블리 로딩 정보 수집](collect-details.md) 문서에서는 런타임에 관리되는 어셈블리 로딩에 대한 자세한 정보를 수집하는 방법을 설명합니다. [dotnet-trace](../diagnostics/dotnet-trace.md) 도구를 사용하여 실행 중인 프로세스의 추적에서 어셈블리 로더 이벤트를 캡처합니다.

---
title: 기계 학습 처리를 위해 여러 파일의 데이터 로드 - ML.NET
description: ML.NET를 사용하여 기계 학습 모델을 빌드하고, 학습하고, 점수를 매기는 데 사용할 여러 파일의 데이터를 로드하는 방법 알아보기
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: fbf5e4b5ab9a1a686edb933bdec818fc532bbf42
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679024"
---
# <a name="load-data-from-multiple-files-for-machine-learning-processing---mlnet"></a><span data-ttu-id="9e28c-103">기계 학습 처리를 위해 여러 파일의 데이터 로드 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="9e28c-103">Load data from multiple files for machine learning processing - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="9e28c-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e28c-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="9e28c-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e28c-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="9e28c-106">이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e28c-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="9e28c-107">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e28c-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="9e28c-108">`TextLoader`를 사용하고, `Read` 메서드에 대한 파일의 배열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e28c-108">Use the `TextLoader`, and specify an array of files to the `Read` method.</span></span> <span data-ttu-id="9e28c-109">파일에는 동일한 스키마(동일한 번호 및 열 형식)가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e28c-109">The files must have the same schema (same number and type of columns):</span></span>

* [<span data-ttu-id="9e28c-110">예제 파일1</span><span class="sxs-lookup"><span data-stu-id="9e28c-110">Example file1</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.train)
* [<span data-ttu-id="9e28c-111">예제 파일2</span><span class="sxs-lookup"><span data-stu-id="9e28c-111">Example file2</span></span>](https://github.com/dotnet/machinelearning/blob/e3a34ae6ae1b25ac96faa0317308703ce943ff95/test/data/adult.test)

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // A boolean column depicting the 'target label'.
        new TextLoader.Column("IsOver50k",DataKind.BL,0),
        // Three text columns.
        new TextLoader.Column("WorkClass",DataKind.TX,1),
        new TextLoader.Column("Education",DataKind.TX,2),
        new TextLoader.Column("MaritalStatus",DataKind.TX,3)
    },
    hasHeader: true
);

// Now read the files (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(exampleFile1, exampleFile2);
```
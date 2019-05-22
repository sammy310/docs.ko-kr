---
title: 데이터 로드
description: 데이터 파일 로드 및 ML.NET에 데이터 스트리밍
ms.date: 05/03/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 6edcc92b610e2e1f5e21c371b9f0aefd0b216d31
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063643"
---
# <a name="load-data-from-file-and-in-memory-sources"></a>파일 및 메모리 내 원본에서 데이터 로드

여기에서는 ML.NET에서의 처리 및 학습을 위해 데이터를 로드하는 방법을 보여 줍니다. 데이터는 기본적으로 파일 또는 실시간/스트리밍 데이터 원본에 저장됩니다.

## <a name="create-the-data-model"></a>데이터 모델 만들기

ML.NET을 사용하면 클래스를 통해 데이터 모델을 정의할 수 있습니다. 다음과 같은 입력 데이터를 가정하겠습니다.

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

아래 코드 조각을 나타내는 데이터 모델을 만듭니다.

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }
 
    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

### <a name="annotating-the-data-model-with-column-attributes"></a>열 특성을 사용하여 데이터 모델에 주석 지정

특성은 데이터 모델과 데이터 원본에 대한 더 상세한 정보를 ML.NET에 제공합니다.

[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) 특성은 속성의 열 인덱스를 지정합니다.

> [!IMPORTANT]
> [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)은 파일에서 데이터를 로드할 때만 필요합니다.

다음과 같이 열을 로드합니다. 
- `HousingData` 클래스에서 `Size` 및 `CurrentPrices` 같은 개별 열
- `HousingData` 클래스에서 `HistoricalPrices` 같이 벡터 형식으로 한 번에 여러 열

벡터 속성이 있는 경우 [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 특성을 데이터 모델의 속성에 적용합니다. 벡터의 모든 요소는 같은 반드시 형식이어야 합니다.

ML.NET은 열 이름으로 작동합니다. 열 이름을 속성 이름과 다르게 변경하려면 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 특성을 사용합니다. 메모리 내 개체를 만들 때도 속성 이름을 사용하여 개체를 만듭니다. 그러나 데이터 처리 및 기계 학습 모델 빌드를 위해 ML.NET은 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 특성에서 제공한 값으로 속성을 재정의 및 참조합니다.

## <a name="load-data-from-a-single-file"></a>단일 파일에서 데이터 로드

파일에서 데이터를 로드하려면 로드할 데이터에 대해 데이터 모델에 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 메서드를 사용합니다. `separatorChar` 매개 변수는 기본적으로 탭으로 구분되므로 필요에 맞게 데이터 파일을 변경합니다. 파일에 헤더가 있으면 `hasHeader` 매개 변수 `true`로 설정하여 파일의 첫 줄을 무시하고 두 번째 줄부터 데이터를 로드하기 시작합니다.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a>여러 파일에서 데이터 로드

데이터가 여러 파일에 저장되어 있고 데이터 스키마가 같은 경우라면 ML.NET에서 같은 디렉터리 또는 여러 디렉터리에 있는 여러 파일에서 데이터를 로드할 수 있습니다.

### <a name="load-from-files-in-a-single-directory"></a>단일 디렉터리의 파일에서 로드

모든 데이터 파일이 같은 디렉터리에 있으면 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 메서드에서 와일드카드를 사용합니다.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a>여러 디렉터리의 파일에서 로드

여러 디렉터리에서 데이터를 로드하려면 [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) 메서드를 사용하여 [`TextLoader`](xref:Microsoft.ML.Data.TextLoader)를 만듭니다. 그런 다음, [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) 메서드를 사용하고 개별 파일 경로를 지정합니다(와일드카드를 사용할 수 없음).

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-streaming-source"></a>스트리밍 원본에서 데이터 로드

ML.NET에서는 디스크에 저장된 데이터의 로드 외에도, 다음을 망라한 다양한 스트리밍 원본에서의 데이터 로드를 지원합니다.

- 메모리 내 컬렉션
- JSON/XML
- Databases

> [!IMPORTANT]
> 스트리밍 원본을 사용할 때는 ML.NET이 메모리 내 컬렉션 형태의 입력을 기대합니다. 따라서 JSON/XML 등의 원본을 사용할 때는 데이터 형식이 메모리 내 컬렉션이 되게 합니다.

다음 메모리 내 컬렉션을 지정합니다.

```csharp
HousingData[] inMemoryCollection = new HousingData[]
{
    new HousingData
    {
        Size =700f,
        HistoricalPrices = new float[]
        {
            100000f, 3000000f, 250000f
        },
        CurrentPrice = 500000f
    },
    new HousingData
    {
        Size =1000f,
        HistoricalPrices = new float[]
        {
            600000f, 400000f, 650000f
        },
        CurrentPrice=700000f
    }
};
```

[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) 메서드로 메모리 내 컬렉션을 [`IDataView`](xref:Microsoft.ML.IDataView)에 로드합니다.

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

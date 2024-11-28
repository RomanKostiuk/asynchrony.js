function fetchData(url) {
    return new Promise((resolve, reject) => {
        console.log(`Fetching data from ${url}...`);

        setTimeout(() => {
            if (Math.random() > 0.2) {
                resolve({ data: `Data successfully retrieved from ${url}`, status: 200 });
            } else {
                reject(new Error(`Failed to fetch data from ${url}`));
            }
        }, 2000);
    });
}
async function getData() {
    const url = "https://api.example.com/data";

    try {
        console.log("Request started...");
        const response = await fetchData(url);
        console.log("Success:", response.data);
    } catch (error) {
        console.error("Error:", error.message);
    } finally {
        console.log("Request finished.");
    }
}

(async () => {
  try {
    const [data1, data2, data3] = await Promise.all([
      fetch('https://jsonplaceholder.typicode.com/todos/1')
        .then(res => {
          if (!res.ok) throw new Error(`Error ${res.status}`);
          return res.json();
        }),
      fetch('https://jsonplaceholder.typicode.com/todos/2')
        .then(res => {
          if (!res.ok) throw new Error(`Error ${res.status}`);
          return res.json();
        }),
      fetch('https://jsonplaceholder.typicode.com/todos/3')
        .then(res => {
          if (!res.ok) throw new Error(`Error ${res.status}`);
          return res.json();
        })
    ]);

    console.log('Results:', data1, data2, data3);
  } catch (err) {
    console.error('One or more fetches failed:', err);
  }
})(); wi

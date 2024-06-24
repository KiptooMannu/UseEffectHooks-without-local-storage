![image](https://github.com/KiptooMannu/UseEffectHooks-without-local-storage/assets/149665572/09f3b3ca-422e-4b7f-8912-edb2ac80e18a)



Fetching Data: We define an async function fetchData within the useEffect hook to fetch the data from the API. This function uses await to wait for the fetch to complete and then processes the response. If the fetch is successful, we update the users state with the fetched data and set loading to false. If an error occurs, we catch it and update the error state.


useEffect(() => {
  const fetchData = async () => {
    try {
      const response = await fetch('https://jsonplaceholder.typicode.com/users');
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }
      const data = await response.json();
      setUsers(data);
      setLoading(false);
    } catch (error) {
      setError(error);
      setLoading(false);
    }
  };

  fetchData();
}, []);




Conditional Rendering: We use conditional rendering to display different UI elements based on the state. If loading is true, we display a loading message. If there is an error, we display the error message. If the data is successfully fetched, we display the list of users.





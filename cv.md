Mun Natalya Vladimirovna

Contacts:
Phone: +7 (776) 181 4444
Email: nataliya.moon@gmail.com
Nickname on discord: Nataliya_Moon

About me:
I am very purposeful, persistent, stress-resistant, not afraid of learning difficulties. I love to study and learn new things. I want to learn programming enough to become a senior manager in a large global company.

Skills:
HTML, CSS, SASS, Typescript, React, RTK Query, Mui, Node.js, Express JS, Git, PostgreSQL, etc.

Experience:
I created a CRM system for a flower shop, worked on the Backend, Frontend and database.

Education: Master of Social Sciences, majoring in journalism.
Courses:
Fullstack JavaScript Developer at Attractor School
Pre-intermediate level of English.


Code example:

const Register = () => {
    const error = useSelector(({usersState}) => usersState.registerError);
    const dispatch = useDispatch();
    const navigate = useNavigate();
    const [state, setState] = useState({
        username: "",
        password: ""
    });

    const location = useLocation();

    useEffect(() => {
        dispatch(setRegisterError(null));
    }, [location]);

    const inputChangeHandler = (e) => {
        const {name, value} = e.currentTarget;

        setState(prevState => {
            return {...prevState, [name]: value};
        });
    };

    const handleSubmit = (e) => {
        e.preventDefault();
        dispatch(registerUser({
            data: {...state},
            callback: () => navigate('/')
        }));
    };

    const getFieldError = (field) => {
        return error?.errors[field]?.message;
    };

    return (
        <ThemeProvider theme={theme}>
            <Container component="main" maxWidth="xs">
                <CssBaseline />
                <Box
                    sx={{
                        marginTop: 8,
                        display: 'flex',
                        flexDirection: 'column',
                        alignItems: 'center',
                    }}
                >
                    <Avatar sx={{ m: 1, bgcolor: 'secondary.main' }}>
                        <LockOutlinedIcon />
                    </Avatar>
                    <Typography component="h1" variant="h5">
                        Register
                    </Typography>
                    <Box component="form" noValidate onSubmit={handleSubmit} sx={{ mt: 3 }}>
                        <Grid container spacing={2}>
                            <FormElement
                                required={true}
                                label="Username"
                                name="username"
                                onChange={inputChangeHandler}
                                value={state.username}
                                error={getFieldError('username')}
                            />
                            <FormElement
                                required={true}
                                name="password"
                                label="Password"
                                type="password"
                                onChange={inputChangeHandler}
                                value={state.password}
                                error={getFieldError('password')}
                            />
                        </Grid>
                        <Button
                            type="submit"
                            fullWidth
                            variant="contained"
                            sx={{ mt: 3, mb: 2 }}
                        >
                            Register
                        </Button>
                        <Grid container justifyContent="flex-end">
                            <Grid item>
                                <Link href="#" variant="body2" component={RouterLink} to={LOGIN}>
                                    Already have an account? Login
                                </Link>
                            </Grid>
                        </Grid>
                    </Box>
                </Box>
            </Container>
        </ThemeProvider>
    );
};

export default Register;